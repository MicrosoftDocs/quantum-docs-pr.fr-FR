---
title: Obtention du nombre de ressources
description: Découvrez comment obtenir des estimations de ressources à l’aide d’un simulateur de traces Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: b8974114a5629fa1928b5774e79aba93fa3d1f7d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856241"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="d80e8-103">Obtention du nombre de ressources</span><span class="sxs-lookup"><span data-stu-id="d80e8-103">Obtaining resource counts</span></span>

<span data-ttu-id="d80e8-104">Le coût de la simulation de $n $ qubits sur les ordinateurs classiques évolue de façon exponentielle avec $n $.</span><span class="sxs-lookup"><span data-stu-id="d80e8-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="d80e8-105">Cela limite beaucoup la taille d’une simulation de chimie quantique que nous pouvons effectuer avec le simulateur d’état complet.</span><span class="sxs-lookup"><span data-stu-id="d80e8-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="d80e8-106">Pour les grandes instances de chimie, nous pouvons néanmoins obtenir des informations utiles.</span><span class="sxs-lookup"><span data-stu-id="d80e8-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="d80e8-107">Ici, nous examinons comment les coûts des ressources, tels que le nombre de grilles de T ou de CNOTIN, pour simuler la chimie peuvent être obtenus de manière automatisée à l’aide du [simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="d80e8-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="d80e8-108">Ces informations nous informent du moment où les ordinateurs quantiques peuvent être suffisamment grands pour exécuter ces algorithmes de chimie de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d80e8-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="d80e8-109">Pour référence, consultez l' `GetGateCount` exemple fourni.</span><span class="sxs-lookup"><span data-stu-id="d80e8-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="d80e8-110">Supposons que nous avons déjà une `FermionHamiltonian` instance de, par exemple, chargée à partir du schéma Broombridge, comme indiqué dans l’exemple [chargement-à partir d’un fichier](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="d80e8-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="d80e8-111">La syntaxe permettant d’obtenir des estimations de ressources est presque identique à l’exécution de l’algorithme sur le simulateur d’état complet.</span><span class="sxs-lookup"><span data-stu-id="d80e8-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="d80e8-112">Nous choisissons simplement un autre ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="d80e8-112">We simply choose a different target machine.</span></span> <span data-ttu-id="d80e8-113">Dans le cadre des estimations de ressources, il suffit d’évaluer le coût d’une seule étape Trotter ou d’un parcours quantique créé par la technique Qubitization.</span><span class="sxs-lookup"><span data-stu-id="d80e8-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="d80e8-114">L’appel de ces algorithmes est le suivant :</span><span class="sxs-lookup"><span data-stu-id="d80e8-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="d80e8-115">Nous configurons maintenant le simulateur de trace pour suivre les ressources qui nous intéressent.</span><span class="sxs-lookup"><span data-stu-id="d80e8-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="d80e8-116">Dans ce cas, nous comptons les opérations de quantum de la primitive en affectant à l’indicateur la valeur `usePrimitiveOperationsCounter` `true` .</span><span class="sxs-lookup"><span data-stu-id="d80e8-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="d80e8-117">Un détail technique `throwOnUnconstraintMeasurement` est défini sur `false` pour éviter les exceptions dans les cas où le Q# code n’affirme pas correctement la probabilité des résultats de mesure, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d80e8-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="d80e8-118">Nous exécutons maintenant l’algorithme Quantum à partir du programme de pilote comme suit.</span><span class="sxs-lookup"><span data-stu-id="d80e8-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```