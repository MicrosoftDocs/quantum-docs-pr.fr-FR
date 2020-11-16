---
title: Compteur de profondeur-Kit de développement quantique
description: 'Découvrez le compteur de profondeur de Microsoft QDK, qui utilise le simulateur de traces Quantum pour rassembler le nombre de niveaux de la profondeur de chaque opération appelée dans un Q# programme.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692107"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="00aeb-103">Simulateur de traces Quantum : compteur de profondeur</span><span class="sxs-lookup"><span data-stu-id="00aeb-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="00aeb-104">Le compteur de profondeur fait partie du [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)du kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="00aeb-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="00aeb-105">Vous pouvez l’utiliser pour rassembler des nombres qui représentent la limite inférieure de la profondeur de chaque opération appelée dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="00aeb-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="00aeb-106">Valeurs de profondeur</span><span class="sxs-lookup"><span data-stu-id="00aeb-106">Depth values</span></span>

<span data-ttu-id="00aeb-107">Par défaut, toutes les opérations ont une profondeur égale à **0** , à l’exception de l' `T` opération, dont la profondeur est égale à **1** .</span><span class="sxs-lookup"><span data-stu-id="00aeb-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1** .</span></span> <span data-ttu-id="00aeb-108">Cela signifie que, par défaut, seule la `T` profondeur des opérations est calculée (ce qui est souvent souhaitable).</span><span class="sxs-lookup"><span data-stu-id="00aeb-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="00aeb-109">Le compteur de profondeur agrège et collecte des statistiques sur tous les bords du [graphique des appels](https://en.wikipedia.org/wiki/Call_graph)de l’opération.</span><span class="sxs-lookup"><span data-stu-id="00aeb-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="00aeb-110">Toutes les <xref:Microsoft.Quantum.Intrinsic> opérations sont exprimées en termes de rotations à qubit unique, d' <xref:Microsoft.Quantum.Intrinsic.T> opérations, d’opérations de Clifford à qubit unique, <xref:Microsoft.Quantum.Intrinsic.CNOT> d’opérations et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="00aeb-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="00aeb-111">Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le `gateTimes` champ de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="00aeb-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="00aeb-112">Appel du compteur de profondeur</span><span class="sxs-lookup"><span data-stu-id="00aeb-112">Invoking the depth counter</span></span>

<span data-ttu-id="00aeb-113">Pour exécuter le simulateur de trace Quantum avec le compteur Depth, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UseDepthCounter` **valeur true** à sa propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="00aeb-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="00aeb-114">Utilisation du compteur Depth dans un programme hôte C#</span><span class="sxs-lookup"><span data-stu-id="00aeb-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="00aeb-115">L’exemple C# qui suit dans cette section calcule la `T` profondeur de l' `CCNOT` opération, en fonction de l' Q# exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="00aeb-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="00aeb-116">Pour vérifier que `CCNOT` a `T` la profondeur **5** et `ApplySampleWithCCNOT` a une `T` profondeur **6** , utilisez le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="00aeb-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6** , use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="00aeb-117">La première partie du programme s’exécute `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="00aeb-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="00aeb-118">La deuxième partie utilise la [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer la `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="00aeb-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="00aeb-119">Enfin, vous pouvez générer toutes les statistiques collectées par le compteur de profondeur au format CSV à l’aide des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="00aeb-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="00aeb-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00aeb-120">See also</span></span>

- <span data-ttu-id="00aeb-121">Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.</span><span class="sxs-lookup"><span data-stu-id="00aeb-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="00aeb-122">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="00aeb-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="00aeb-123">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="00aeb-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="00aeb-124">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API.</span><span class="sxs-lookup"><span data-stu-id="00aeb-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
