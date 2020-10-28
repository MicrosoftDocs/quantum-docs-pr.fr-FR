---
title: Compteur d’opérations primitives-Kit de développement Quantum
description: 'Découvrez le compteur d’opérations primitives Microsoft QDK, qui utilise le simulateur de traces Quantum pour suivre les processus primitifs utilisés par les opérations dans un :::no-loc(Q#)::: programme.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690956"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="fcde9-103">Simulateur de traces Quantum : compteur d’opérations primitives</span><span class="sxs-lookup"><span data-stu-id="fcde9-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="fcde9-104">Le compteur d’opérations primitifs fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="fcde9-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="fcde9-105">Il compte le nombre de processus primitifs utilisés par chaque opération appelée dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="fcde9-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="fcde9-106">Toutes les <xref:Microsoft.Quantum.Intrinsic> opérations sont exprimées en termes de rotations à qubit unique, d’opérations T, d’opérations de Clifford qubit, d’opérations cnotin et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="fcde9-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="fcde9-107">Le compteur opérations primitives agrège et collecte des statistiques sur tous les bords du [graphique des appels](https://en.wikipedia.org/wiki/Call_graph)de l’opération.</span><span class="sxs-lookup"><span data-stu-id="fcde9-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="fcde9-108">Appel du compteur d’opérations primitifs</span><span class="sxs-lookup"><span data-stu-id="fcde9-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="fcde9-109">Pour exécuter le simulateur de trace Quantum avec le compteur d’opérations primitifs, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UsePrimitiveOperationsCounter` **valeur true** à la propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec le `QCTraceSimulatorConfiguration` comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="fcde9-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="fcde9-110">Utilisation du compteur d’opérations primitifs dans un programme hôte C#</span><span class="sxs-lookup"><span data-stu-id="fcde9-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="fcde9-111">L’exemple C# qui suit dans cette section compte le nombre <xref:Microsoft.Quantum.Intrinsic.T> d’opérations nécessaires pour implémenter l' <xref:Microsoft.Quantum.Intrinsic.ccnot> opération, en fonction de l' :::no-loc(Q#)::: exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="fcde9-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.ccnot> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="fcde9-112">Pour vérifier que `CCNOT` requiert sept `T` opérations et qu' `ApplySampleWithCCNOT` elle exécute huit `T` opérations, utilisez le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="fcde9-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="fcde9-113">La première partie du programme s’exécute `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="fcde9-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="fcde9-114">La deuxième partie utilise la [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer le nombre d' `T` opérations exécutées par `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="fcde9-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="fcde9-115">Quand vous appelez `GetMetric` avec deux paramètres de type, elle retourne la valeur de la métrique associée à un bord de graphique d’appel donné.</span><span class="sxs-lookup"><span data-stu-id="fcde9-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="fcde9-116">Dans l’exemple précédent, le programme appelle l' `Primitive.CCNOT` opération dans `ApplySampleWithCCNOT` et, par conséquent, le graphique des appels contient le bord `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="fcde9-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="fcde9-117">Pour récupérer le nombre d' `CNOT` opérations utilisées, ajoutez la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="fcde9-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="fcde9-118">Enfin, vous pouvez générer toutes les statistiques collectées par le compteur d’opérations primitives au format CSV à l’aide des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fcde9-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="fcde9-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcde9-119">See also</span></span>

- <span data-ttu-id="fcde9-120">Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.</span><span class="sxs-lookup"><span data-stu-id="fcde9-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="fcde9-121">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="fcde9-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="fcde9-122">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="fcde9-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="fcde9-123">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API.</span><span class="sxs-lookup"><span data-stu-id="fcde9-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>