---
title: Compteur de profondeur
description: Découvrez le compteur de profondeur Microsoft QDK, qui rassemble le nombre de la profondeur de chaque opération appelée dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274934"
---
# <a name="depth-counter"></a><span data-ttu-id="b98fc-103">Compteur de profondeur</span><span class="sxs-lookup"><span data-stu-id="b98fc-103">Depth Counter</span></span>

<span data-ttu-id="b98fc-104">Le `Depth Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.</span><span class="sxs-lookup"><span data-stu-id="b98fc-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="b98fc-105">Il est utilisé pour regrouper les nombres de la profondeur de chaque opération appelée dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="b98fc-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="b98fc-106">Toutes les opérations de <xref:microsoft.quantum.intrinsic> sont exprimées en termes de rotations à qubit unique, de grilles de T, de portes de qubit Clifford uniques, de portes cnotin et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="b98fc-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="b98fc-107">Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le `gateTimes` champ de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="b98fc-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="b98fc-108">Par défaut, toutes les opérations ont la profondeur 0, à l’exception de la porte T qui a la profondeur 1.</span><span class="sxs-lookup"><span data-stu-id="b98fc-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="b98fc-109">Cela signifie que, par défaut, seule la profondeur des opérations T est calculée (ce qui est souvent souhaitable).</span><span class="sxs-lookup"><span data-stu-id="b98fc-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="b98fc-110">Les statistiques collectées sont agrégées sur tous les bords du graphique des appels d’opérations.</span><span class="sxs-lookup"><span data-stu-id="b98fc-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="b98fc-111">Nous allons maintenant calculer la <xref:microsoft.quantum.intrinsic.t> profondeur de l' <xref:microsoft.quantum.intrinsic.ccnot> opération.</span><span class="sxs-lookup"><span data-stu-id="b98fc-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="b98fc-112">Nous allons utiliser l’exemple de code Q # suivant :</span><span class="sxs-lookup"><span data-stu-id="b98fc-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="b98fc-113">Utilisation du compteur Depth dans un programme C#</span><span class="sxs-lookup"><span data-stu-id="b98fc-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="b98fc-114">Pour vérifier que `CCNOT` a une `T` profondeur 5 et `ApplySampleWithCCNOT` a une `T` profondeur 6, nous pouvons utiliser le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="b98fc-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="b98fc-115">La première partie du programme s’exécute `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="b98fc-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="b98fc-116">Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître la `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="b98fc-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="b98fc-117">Enfin, pour générer toutes les statistiques collectées au `Depth Counter` format CSV, nous pouvons utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b98fc-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="b98fc-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b98fc-118">See also</span></span> ##

- <span data-ttu-id="b98fc-119">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="b98fc-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
