---
title: Compteur d’opérations primitifs
description: Découvrez le compteur d’opérations primitives de Microsoft QDK, qui effectue le suivi du nombre d’exécutions de primitives utilisées par les opérations dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274893"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="0174f-103">Compteur d’opérations primitifs</span><span class="sxs-lookup"><span data-stu-id="0174f-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="0174f-104">Le `Primitive Operations Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.</span><span class="sxs-lookup"><span data-stu-id="0174f-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0174f-105">Il compte le nombre d’exécutions de primitives utilisées par chaque opération appelée dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="0174f-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="0174f-106">Toutes les opérations de `Microsoft.Quantum.Intrinsic` sont exprimées en termes de rotations à qubit unique, de grilles de T, de portes de qubit Clifford uniques, de portes cnotin et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="0174f-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="0174f-107">Les statistiques collectées sont agrégées sur les bords du graphique des appels d’opérations.</span><span class="sxs-lookup"><span data-stu-id="0174f-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="0174f-108">Nous allons maintenant compter le nombre `T` de portes nécessaires pour implémenter l' `CCNOT` opération.</span><span class="sxs-lookup"><span data-stu-id="0174f-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="0174f-109">Utilisation du compteur d’opérations primitifs dans un programme C#</span><span class="sxs-lookup"><span data-stu-id="0174f-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="0174f-110">Pour vérifier que `CCNOT` requiert 7 `T` portes et que `ApplySampleWithCCNOT` exécute 8 portes, `T` nous pouvons utiliser le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="0174f-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0174f-111">La première partie du programme s’exécute `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="0174f-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="0174f-112">Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour récupérer le nombre de portes T exécutées par `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="0174f-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0174f-113">Lorsque `GetMetric` est appelé avec deux paramètres de type, il retourne la valeur de la métrique associée à un bord de graphique d’appel donné.</span><span class="sxs-lookup"><span data-stu-id="0174f-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="0174f-114">Dans notre exemple, `Primitive.CCNOT` l’opération est appelée dans `ApplySampleWithCCNOT` et par conséquent, le graphique des appels contient le bord `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="0174f-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="0174f-115">Pour connaître le nombre de `CNOT` portes utilisées, nous pouvons ajouter la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="0174f-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="0174f-116">Enfin, pour afficher toutes les statistiques collectées par le compteur de porte au format CSV, nous pouvons utiliser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0174f-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="0174f-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0174f-117">See also</span></span> ##

- <span data-ttu-id="0174f-118">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="0174f-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
