---
title: Obtention d’estimations du niveau d’énergie
description: 'Parcourez un exemple de Q# programme qui estime les valeurs de niveau d’énergie de l’hydrogène moléculaire.'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691530"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="ab1d8-103">Obtention d’estimations du niveau d’énergie</span><span class="sxs-lookup"><span data-stu-id="ab1d8-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="ab1d8-104">L’estimation des valeurs des niveaux énergétiques est l’une des principales applications de la chimie Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="ab1d8-105">Cet article décrit comment effectuer cette procédure pour l’exemple canonique d’hydrogène moléculaire.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="ab1d8-106">L’exemple référencé dans cette section se trouve [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) dans le référentiel d’exemples chimie.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="ab1d8-107">Un exemple visuel qui trace la sortie est la [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) démonstration.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="ab1d8-108">Estimation des valeurs énergétiques de l’hydrogène moléculaire</span><span class="sxs-lookup"><span data-stu-id="ab1d8-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="ab1d8-109">La première étape consiste à construire la Hamilton représentant l’hydrogène moléculaire.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="ab1d8-110">Bien que vous puissiez construire ce code à l’aide de l’outil NWChem, par souci de concision, cet exemple ajoute les termes de la Hamilton manuellement.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="ab1d8-111">La simulation de la Hamilton requiert la conversion des opérateurs fermion en opérateurs qubit.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="ab1d8-112">Cette conversion s’effectue par le biais de l’encodage Jordan-Wigner comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab1d8-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="ab1d8-113">Ensuite, transmettez `qSharpData` , qui représente le « Hamilton », à la `TrotterStepOracle` fonction.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="ab1d8-114">`TrotterStepOracle` retourne une opération de Quantum qui correspond approximativement à l’évolution en temps réel de l’activité Hamilton.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="ab1d8-115">Pour plus d’informations, consultez [simulation de Dynamics Hamilton](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="ab1d8-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="ab1d8-116">À ce stade, vous pouvez utiliser les [algorithmes d’estimation de phase](xref:microsoft.quantum.libraries.characterization) de la bibliothèque standard pour apprendre l’énergie de l’état du sol à l’aide de la simulation précédente.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="ab1d8-117">Cela nécessite de préparer une bonne approximation à l’état de la terre Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="ab1d8-118">Des suggestions pour ces approximations sont fournies dans le [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schéma.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="ab1d8-119">Toutefois, en l’absence de ces suggestions, l’approche par défaut ajoute un certain nombre d' `hamiltonian.NElectrons` électrons à greedily, réduisant ainsi les énergies à un terme à un seul électron.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="ab1d8-120">Les fonctions et opérations d’estimation de phase sont fournies en notation DocFX dans l’espace de noms [Microsoft. Quantum. charactering](xref:Microsoft.Quantum.Characterization) .</span><span class="sxs-lookup"><span data-stu-id="ab1d8-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="ab1d8-121">L’extrait de code suivant montre comment la sortie de l’évolution en temps réel de la bibliothèque de simulation chimie s’intègre à l’évaluation de la phase Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="ab1d8-122">Vous pouvez maintenant appeler le Q# code à partir du programme hôte.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="ab1d8-123">Le code C# suivant crée un simulateur d’état complet et s’exécute `GetEnergyByTrotterization` pour obtenir l’énergie de l’état du sol.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="ab1d8-124">L’opération retourne deux paramètres :</span><span class="sxs-lookup"><span data-stu-id="ab1d8-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="ab1d8-125">`energyEst` est l’estimation de l’énergie de l’état du sol et doit être proche de `-1.137` en moyenne.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="ab1d8-126">`phaseEst` est la phase brute retournée par l’algorithme d’estimation de la phase.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="ab1d8-127">Cela est utile pour diagnostiquer les alias lorsqu’il se produit en raison d’une `trotterStep` valeur trop grande.</span><span class="sxs-lookup"><span data-stu-id="ab1d8-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
