---
title: Simulateur de traces quantiques - Kit de développement Microsoft Quantum
description: Découvrez comment utiliser le simulateur de traces d’ordinateur quantiques de Microsoft pour déboguer du code classique et estimer les besoins en ressources d’un programme Q#.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 2e2d9f8494d8709fba34123793cecce4011b609a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690829"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="d6891-103">Simulateur de traces quantiques - Kit de développement Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="d6891-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="d6891-104">La classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> du QDK exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="d6891-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="d6891-105">Pour cette raison, le simulateur de traces quantiques peut exécuter des programmes quantiques qui utilisent des milliers de qubits.</span><span class="sxs-lookup"><span data-stu-id="d6891-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="d6891-106">Il est utile à deux fins principales :</span><span class="sxs-lookup"><span data-stu-id="d6891-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="d6891-107">le débogage du code classique qui fait partie d’un programme quantique ;</span><span class="sxs-lookup"><span data-stu-id="d6891-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="d6891-108">l’estimation des ressources requises pour exécuter une instance donnée d’un programme quantique sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="d6891-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="d6891-109">En fait, l’[estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator), qui fournit un ensemble de métriques plus limité, repose sur le simulateur de traces.</span><span class="sxs-lookup"><span data-stu-id="d6891-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="d6891-110">Appel du simulateur de traces quantiques</span><span class="sxs-lookup"><span data-stu-id="d6891-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="d6891-111">Vous pouvez utiliser le simulateur de traces quantiques pour exécuter n’importe quelle opération Q#.</span><span class="sxs-lookup"><span data-stu-id="d6891-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="d6891-112">Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `QCTraceSimulator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.</span><span class="sxs-lookup"><span data-stu-id="d6891-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d6891-113">Notez que, contrairement à la classe `QuantumSimulator`, la classe `QCTraceSimulator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="d6891-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="d6891-114">Calcul de la probabilité des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="d6891-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="d6891-115">Étant donné que le simulateur de traces quantiques ne simule pas l’état quantique réel, il ne peut pas calculer la probabilité des résultats de mesure dans le cadre d’une opération.</span><span class="sxs-lookup"><span data-stu-id="d6891-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="d6891-116">Par conséquent, si une opération comprend des mesures, vous devez fournir explicitement ces probabilités à l’aide de l’opération <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> à partir de l’espace de noms <xref:Microsoft.Quantum.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="d6891-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation from the <xref:Microsoft.Quantum.Diagnostics> namespace.</span></span> <span data-ttu-id="d6891-117">L'exemple suivant illustre ce mécanisme :</span><span class="sxs-lookup"><span data-stu-id="d6891-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="d6891-118">Lorsque le simulateur de traces quantiques rencontre `AssertMeasurementProbability`, il enregistre que la mesure de `PauliZ` sur `source` et `q` doit avoir un résultat de `Zero` avec une probabilité de **0,5** .</span><span class="sxs-lookup"><span data-stu-id="d6891-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5** .</span></span> <span data-ttu-id="d6891-119">Lorsque plus tard, il exécutera l’opération `M`, il trouvera les valeurs enregistrées des probabilités de résultat. En outre, `M` retournera `Zero` ou `One`, avec une probabilité de **0,5** .</span><span class="sxs-lookup"><span data-stu-id="d6891-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5** .</span></span> <span data-ttu-id="d6891-120">Quand le même code est exécuté sur un simulateur qui effectue le suivi de l’état quantique, ce simulateur vérifie que les probabilités fournies dans `AssertMeasurementProbability` sont correctes.</span><span class="sxs-lookup"><span data-stu-id="d6891-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="d6891-121">Notez que s’il existe au moins une opération de mesure qui n’est pas annotée à l’aide de `AssertMeasurementProbability`, le simulateur lèvera une [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="d6891-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="d6891-122">Outils du simulateur de traces quantiques</span><span class="sxs-lookup"><span data-stu-id="d6891-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="d6891-123">Le QDK comprend cinq outils que vous pouvez utiliser avec le simulateur de traces quantiques pour détecter les bogues de vos programmes et réaliser des estimations pour les ressources de votre programme quantique :</span><span class="sxs-lookup"><span data-stu-id="d6891-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="d6891-124">Outil</span><span class="sxs-lookup"><span data-stu-id="d6891-124">Tool</span></span> | <span data-ttu-id="d6891-125">Description</span><span class="sxs-lookup"><span data-stu-id="d6891-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="d6891-126">Vérificateur d’entrées distinctes</span><span class="sxs-lookup"><span data-stu-id="d6891-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="d6891-127">Recherche les conflits potentiels avec les qubits partagés</span><span class="sxs-lookup"><span data-stu-id="d6891-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="d6891-128">Vérificateur d’utilisation de qubits non valides</span><span class="sxs-lookup"><span data-stu-id="d6891-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="d6891-129">Vérifie si le programme applique une opération sur un qubit déjà publié</span><span class="sxs-lookup"><span data-stu-id="d6891-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="d6891-130">Compteur d’opérations primitives</span><span class="sxs-lookup"><span data-stu-id="d6891-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="d6891-131">Compte le nombre de primitives utilisées par chaque opération appelée dans un programme quantique</span><span class="sxs-lookup"><span data-stu-id="d6891-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="d6891-132">Compteur de profondeur</span><span class="sxs-lookup"><span data-stu-id="d6891-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="d6891-133">Rassemble les nombres qui représentent la limite inférieure de la profondeur de chaque opération appelée dans un programme quantique</span><span class="sxs-lookup"><span data-stu-id="d6891-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="d6891-134">Compteur de largeur</span><span class="sxs-lookup"><span data-stu-id="d6891-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="d6891-135">Compte le nombre de qubits alloués et empruntés par chaque opération dans un programme quantique</span><span class="sxs-lookup"><span data-stu-id="d6891-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="d6891-136">Chacun de ces outils est activé en définissant les indicateurs appropriés dans `QCTraceSimulatorConfiguration`, puis en passant la configuration à la déclaration `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="d6891-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="d6891-137">Pour plus d’informations sur l’utilisation de chacun de ces outils, consultez les liens fournis dans la liste précédente.</span><span class="sxs-lookup"><span data-stu-id="d6891-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="d6891-138">Pour plus d’informations sur la configuration de `QCTraceSimulator`, consultez [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d6891-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="d6891-139">Méthodes QCTraceSimulator</span><span class="sxs-lookup"><span data-stu-id="d6891-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="d6891-140">`QCTraceSimulator` comprend plusieurs méthodes intégrées permettant de récupérer les valeurs des métriques suivies au cours d’une opération quantique.</span><span class="sxs-lookup"><span data-stu-id="d6891-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="d6891-141">Vous trouverez des exemples pour les méthodes [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) et [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) dans les articles [Compteur d’opérations primitives](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) et [Compteur de largeur](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="d6891-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="d6891-142">Pour plus d’informations sur les méthodes disponibles, consultez [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) dans la référence de l’API Q#.</span><span class="sxs-lookup"><span data-stu-id="d6891-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d6891-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6891-143">See also</span></span>

- [<span data-ttu-id="d6891-144">Estimateur de ressources quantiques</span><span class="sxs-lookup"><span data-stu-id="d6891-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="d6891-145">Simulateur Toffoli quantique</span><span class="sxs-lookup"><span data-stu-id="d6891-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="d6891-146">Simulateur d’état complet quantique</span><span class="sxs-lookup"><span data-stu-id="d6891-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 