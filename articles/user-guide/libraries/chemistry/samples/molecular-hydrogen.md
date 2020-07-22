---
title: Obtention d’estimations du niveau d’énergie
description: 'Parcourez un exemple de programme Q # qui estime les valeurs de niveau d’énergie de l’hydrogène moléculaire.'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: b26538980366cf4cbe01fc2ef59580ae182f1e8a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871566"
---
# <a name="obtaining-energy-level-estimates"></a>Obtention d’estimations du niveau d’énergie
L’estimation des valeurs des niveaux énergétiques est l’une des principales applications de la chimie Quantum. Cet article décrit comment effectuer cette procédure pour l’exemple canonique d’hydrogène moléculaire. L’exemple référencé dans cette section se trouve [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) dans le référentiel d’exemples chimie. Un exemple visuel qui trace la sortie est la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) démonstration.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Estimation des valeurs énergétiques de l’hydrogène moléculaire

La première étape consiste à construire la Hamilton représentant l’hydrogène moléculaire. Bien que vous puissiez construire ce code à l’aide de l’outil NWChem, par souci de concision, cet exemple ajoute les termes de la Hamilton manuellement.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

La simulation de la Hamilton requiert la conversion des opérateurs fermion en opérateurs qubit. Cette conversion est effectuée par le biais de l’encodage Jordanie-Wigner comme suit :

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Ensuite, transmettez `qSharpData` , qui représente le « Hamilton », à la `TrotterStepOracle` fonction. `TrotterStepOracle`retourne une opération de Quantum qui correspond approximativement à l’évolution en temps réel de l’activité Hamilton. Pour plus d’informations, consultez [simulation de Dynamics Hamilton](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

À ce stade, vous pouvez utiliser les [algorithmes d’estimation de phase](xref:microsoft.quantum.libraries.characterization) de la bibliothèque standard pour apprendre l’énergie de l’état du sol à l’aide de la simulation précédente. Cela nécessite de préparer une bonne approximation à l’état de la terre Quantum. Des suggestions pour ces approximations sont fournies dans le [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schéma. Toutefois, en l’absence de ces suggestions, l’approche par défaut ajoute un certain nombre d' `hamiltonian.NElectrons` électrons à greedily, réduisant ainsi les énergies à un terme à un seul électron. Les fonctions et opérations d’estimation de phase sont fournies en notation DocFX dans l’espace de noms [Microsoft. Quantum. charactering](xref:microsoft.quantum.characterization) .

L’extrait de code suivant montre comment la sortie de l’évolution en temps réel de la bibliothèque de simulation chimie s’intègre à l’évaluation de la phase Quantum.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

Vous pouvez maintenant appeler le code Q # à partir du programme hôte. Le code C# suivant crée un simulateur d’état complet et s’exécute `GetEnergyByTrotterization` pour obtenir l’énergie de l’état du sol.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

L’opération retourne deux paramètres : 

- `energyEst`est l’estimation de l’énergie de l’état du sol et doit être proche de `-1.137` en moyenne. 
- `phaseEst`est la phase brute retournée par l’algorithme d’estimation de la phase. Cela est utile pour diagnostiquer les alias lorsqu’il se produit en raison d’une `trotterStep` valeur trop grande.
