---
title: Obtention d’estimations de niveau d’énergie | Microsoft Docs
description: Obtention de documents sur les estimations de niveau d’énergie
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 0fd457b152083af364d924502c18bc0813e34b83
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442581"
---
# <a name="obtaining-energy-level-estimates"></a>Obtention d’estimations du niveau d’énergie
L’estimation des valeurs des niveaux énergétiques est l’une des principales applications de la chimie Quantum. Ici, nous décrivons comment cela peut être effectué pour l’exemple canonique d’hydrogène moléculaire. L’exemple référencé dans cette section est `MolecularHydrogen` dans le référentiel d’exemples chimie. Un exemple visuel qui trace le résultat est la démonstration `MolecularHydrogenGUI`.

Notre première étape consiste à construire la Hamilton représentant l’hydrogène moléculaire. Bien que cela puisse être construit à l’aide de l’outil NWChem, nous ajoutons manuellement des termes de brièveté à des fins de concision dans cet exemple.

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Le fait de simuler le « Hamilton » nécessite que nous puissions convertir les opérateurs fermion en opérateurs qubit. Cette conversion est effectuée par le biais de l’encodage Jordanie-Wigner comme suit.

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Nous passons maintenant le `qSharpData` représentant la Hamilton à la fonction de `TrotterStepOracle` dans la simulation de la dynamique de la [Hamilton](xref:microsoft.quantum.libraries.standard.algorithms). `TrotterStepOracle` retourne une opération de Quantum qui correspond approximativement à l’évolution réelle de la réalité.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Nous pouvons maintenant utiliser les algorithmes d’estimation de phase de la bibliothèque standard pour apprendre l’énergie de l’état du sol à l’aide de la simulation ci-dessus. Cela nécessite de préparer une bonne approximation à l’état de la terre Quantum. Les suggestions relatives à ces approximations sont fournies dans le schéma de `Broombridge`, mais absentes de ces suggestions, l’approche par défaut ajoute un certain nombre de `hamiltonian.NElectrons` ELECTRONS à greedily, réduisant ainsi les énergies à un seul terme à un seul électron. Les fonctions et opérations d’estimation de phase se trouvent dans l' [espace de noms Microsoft. Quantum. charactering](xref:microsoft.quantum.characterization in DocFX notation).

L’extrait de code suivant montre comment la sortie en temps réel de la bibliothèque de simulation chimie peut être intégrée à l’évaluation de la phase de Quantum.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

Ce code Q # peut désormais être appelé à partir du programme du pilote. Dans l’exemple suivant, nous créons un simulateur d’état complet et exécutons `GetEnergyByTrotterization` pour obtenir l’énergie de l’état du sol.

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Notez que deux paramètres sont retournés. `energyEst` est l’estimation de l’énergie de l’état du sol et doit être environ `-1.137` en moyenne. `phaseEst` est la phase brute renvoyée par l’algorithme d’estimation de la phase et est utile pour diagnostiquer le moment où un alias se produit en raison d’un `trotterStep` trop grand.
