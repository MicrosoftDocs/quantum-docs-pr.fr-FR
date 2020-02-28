---
title: Obtention du nombre de ressources
description: Découvrez comment obtenir des estimations de ressources à l’aide d’un simulateur de traces Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907832"
---
# <a name="obtaining-resource-counts"></a>Obtention du nombre de ressources

Le coût de la simulation de $n $ qubits sur les ordinateurs classiques évolue de façon exponentielle avec $n $. Cela limite beaucoup la taille d’une simulation de chimie quantique que nous pouvons effectuer avec le simulateur d’état complet. Pour les grandes instances de chimie, nous pouvons néanmoins obtenir des informations utiles. Ici, nous examinons comment les coûts des ressources, tels que le nombre de grilles de T ou de CNOTIN, pour simuler la chimie peuvent être obtenus de manière automatisée à l’aide du [simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Ces informations nous informent du moment où les ordinateurs quantiques peuvent être suffisamment grands pour exécuter ces algorithmes de chimie de Quantum. Pour référence, consultez l’exemple de `GetGateCount` fourni.

Supposons que nous avons déjà une instance de `FermionHamiltonian`, par exemple, chargée à partir du schéma Broombridge comme indiqué dans l’exemple [chargement-à partir d’un fichier](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

La syntaxe permettant d’obtenir des estimations de ressources est presque identique à l’exécution de l’algorithme sur le simulateur d’état complet. Nous choisissons simplement un autre ordinateur cible. Dans le cadre des estimations de ressources, il suffit d’évaluer le coût d’une seule étape Trotter ou d’un parcours quantique créé par la technique Qubitization. L’appel de ces algorithmes est le suivant :

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

Nous configurons maintenant le simulateur de trace pour suivre les ressources qui nous intéressent. Dans ce cas, nous comptons les opérations de quantum de la primitive en affectant à l’indicateur `usePrimitiveOperationsCounter` la valeur `true`. Une `throwOnUnconstraintMeasurement` de détails techniques est définie sur `false` pour éviter les exceptions dans les cas où le code Q # n’affirme pas correctement la probabilité des résultats de mesure, le cas échéant.

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

Nous exécutons maintenant l’algorithme Quantum à partir du programme de pilote comme suit.

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