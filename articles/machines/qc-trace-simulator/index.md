---
title: Simulateur de traces d’ordinateur quantique | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035133"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="2c0ae-103">Simulateur de traces quantiques</span><span class="sxs-lookup"><span data-stu-id="2c0ae-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="2c0ae-104">Le simulateur de traces quantiques de Microsoft exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="2c0ae-105">Pour cette raison, le simulateur de traces peut exécuter des programmes quantiques qui utilisent des milliers de qubits.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="2c0ae-106">Il est utile à deux fins principales :</span><span class="sxs-lookup"><span data-stu-id="2c0ae-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="2c0ae-107">le débogage du code classique qui fait partie d’un programme quantique ;</span><span class="sxs-lookup"><span data-stu-id="2c0ae-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="2c0ae-108">l’estimation des ressources requises pour exécuter une instance donnée d’un programme quantique sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="2c0ae-109">Le simulateur de traces s’appuie sur des informations supplémentaires fournies par l’utilisateur lorsque des mesures doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="2c0ae-110">Pour plus d’informations à ce sujet, consultez la section [Génération de la probabilité des résultats de mesure](#providing-the-probability-of-measurement-outcomes).</span><span class="sxs-lookup"><span data-stu-id="2c0ae-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="2c0ae-111">Génération de la probabilité des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="2c0ae-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="2c0ae-112">Il existe deux types de mesures qui apparaissent dans les algorithmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="2c0ae-113">Le premier type joue un rôle auxiliaire dans lequel l’utilisateur connaît généralement la probabilité des résultats.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="2c0ae-114">Dans ce cas, l’utilisateur peut écrire des <xref:microsoft.quantum.primitive.assertprob> à partir de l’espace de noms <xref:microsoft.quantum.primitive> pour exprimer cette connaissance.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-114">In this case the user can write <xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace to express this knowledge.</span></span> <span data-ttu-id="2c0ae-115">L'exemple suivant illustre ce mécanisme :</span><span class="sxs-lookup"><span data-stu-id="2c0ae-115">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="2c0ae-116">Lorsque le simulateur de traces exécute `AssertProb`, il enregistre que la mesure de `PauliZ` sur `source` et `ancilla` doit avoir un résultat de `Zero` avec une probabilité de 0,5.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="2c0ae-117">Lorsque le simulateur exécute `M` plus tard, il trouve les valeurs enregistrées des probabilités de résultat et `M` retourne `Zero` ou `One` avec une probabilité de 0,5.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="2c0ae-118">Quand le même code est exécuté sur un simulateur qui effectue le suivi de l’état quantique, ce simulateur vérifie que les probabilités fournies dans `AssertProb` sont correctes.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="2c0ae-119">Exécution de votre programme avec le simulateur de traces d’ordinateur quantique</span><span class="sxs-lookup"><span data-stu-id="2c0ae-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="2c0ae-120">Le simulateur de traces d’ordinateur quantique peut être considéré comme une autre machine cible.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="2c0ae-121">Le programme pilote en C# permettant de l’utiliser est très similaire à celui de tout autre simulateur quantique :</span><span class="sxs-lookup"><span data-stu-id="2c0ae-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="2c0ae-122">Notez que s’il existe au moins une mesure qui n’est pas annotée à l’aide de `AssertProb`, le simulateur lèvera `UnconstrainedMeasurementException` à partir de l’espace de noms `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="2c0ae-123">Pour plus d’informations, consultez la documentation de l’API sur [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).</span><span class="sxs-lookup"><span data-stu-id="2c0ae-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="2c0ae-124">Outre l’exécution de programmes quantiques, le simulateur de traces dispose de cinq composants permettant la détection des bogues dans les programmes et l’exécution d’estimations de ressources pour les programmes quantiques :</span><span class="sxs-lookup"><span data-stu-id="2c0ae-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="2c0ae-125">Vérificateur d’entrées distinctes</span><span class="sxs-lookup"><span data-stu-id="2c0ae-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="2c0ae-126">Vérificateur d’utilisation de qubits non valides</span><span class="sxs-lookup"><span data-stu-id="2c0ae-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="2c0ae-127">Compteur d’opérations primitives</span><span class="sxs-lookup"><span data-stu-id="2c0ae-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="2c0ae-128">Compteur de profondeur du circuit</span><span class="sxs-lookup"><span data-stu-id="2c0ae-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="2c0ae-129">Compteur de largeur du circuit</span><span class="sxs-lookup"><span data-stu-id="2c0ae-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="2c0ae-130">Chacun de ces composants peut être activé en définissant les indicateurs appropriés dans `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="2c0ae-131">Vous trouverez plus d’informations sur l’utilisation de chacun de ces composants dans les fichiers de référence correspondants.</span><span class="sxs-lookup"><span data-stu-id="2c0ae-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="2c0ae-132">Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="2c0ae-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c0ae-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c0ae-133">See also</span></span>
<span data-ttu-id="2c0ae-134">Référence en C# du [simulateur de traces](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) d’ordinateur quantique</span><span class="sxs-lookup"><span data-stu-id="2c0ae-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

