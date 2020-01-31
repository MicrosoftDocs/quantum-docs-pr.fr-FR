---
title: Compteur de profondeur | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820468"
---
# <a name="depth-counter"></a><span data-ttu-id="66645-103">Compteur de profondeur</span><span class="sxs-lookup"><span data-stu-id="66645-103">Depth Counter</span></span>

<span data-ttu-id="66645-104">Le `Depth Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.</span><span class="sxs-lookup"><span data-stu-id="66645-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="66645-105">Il est utilisé pour regrouper les nombres de la profondeur de chaque opération appelée dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="66645-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="66645-106">Toutes les opérations à partir de <xref:microsoft.quantum.intrinsic> sont exprimées en termes de rotations qubit uniques, de grilles de qubit Clifford uniques, de portes CNOTIN et de mesures de qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="66645-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="66645-107">Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le champ `gateTimes` de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="66645-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="66645-108">Par défaut, toutes les opérations ont la profondeur 0, à l’exception de la porte T qui a la profondeur 1.</span><span class="sxs-lookup"><span data-stu-id="66645-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="66645-109">Cela signifie que, par défaut, seule la profondeur des opérations T est calculée (ce qui est souvent souhaitable).</span><span class="sxs-lookup"><span data-stu-id="66645-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="66645-110">Les statistiques collectées sont agrégées sur tous les bords du graphique des appels d’opérations.</span><span class="sxs-lookup"><span data-stu-id="66645-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="66645-111">Calculons à présent le <xref:microsoft.quantum.intrinsic.t> profondeur de l’opération <xref:microsoft.quantum.intrinsic.ccnot>.</span><span class="sxs-lookup"><span data-stu-id="66645-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="66645-112">Nous allons utiliser l’exemple de code Q # suivant :</span><span class="sxs-lookup"><span data-stu-id="66645-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="66645-113">Utilisation du compteur de profondeur C# dans un programme</span><span class="sxs-lookup"><span data-stu-id="66645-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="66645-114">Pour vérifier que `CCNOT` a `T` profondeur 5 et que `ApplySampleWithCCNOT` a `T` profondeur 6, nous pouvons utiliser C# le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66645-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="66645-115">La première partie du programme exécute `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="66645-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="66645-116">Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître l' `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="66645-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="66645-117">Enfin, pour générer toutes les statistiques collectées par `Depth Counter` au format CSV, nous pouvons utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="66645-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="66645-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66645-118">See also</span></span> ##

- <span data-ttu-id="66645-119">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="66645-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
