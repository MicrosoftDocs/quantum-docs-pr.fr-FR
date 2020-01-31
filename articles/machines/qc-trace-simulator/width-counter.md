---
title: Compteur de largeur | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820366"
---
# <a name="width-counter"></a><span data-ttu-id="689e0-103">Compteur de largeur</span><span class="sxs-lookup"><span data-stu-id="689e0-103">Width Counter</span></span>

<span data-ttu-id="689e0-104">Le `Width Counter` compte le nombre d’qubits alloués et empruntés par chaque opération.</span><span class="sxs-lookup"><span data-stu-id="689e0-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="689e0-105">Toutes les opérations de l’espace de noms `Microsoft.Quantum.Intrinsic` sont exprimées en termes de rotations qubit simples, de portes T, de portes qubit Clifford simples, de portes CNOTIN et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="689e0-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="689e0-106">Certaines opérations primitives peuvent allouer des qubits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="689e0-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="689e0-107">Par exemple, multiplier les portes `X` contrôlées ou contrôler les portes `T`.</span><span class="sxs-lookup"><span data-stu-id="689e0-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="689e0-108">Nous allons calculer le nombre de qubits supplémentaires alloués par l’implémentation d’une porte de `X` contrôlée par multiplication :</span><span class="sxs-lookup"><span data-stu-id="689e0-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="689e0-109">Utilisation d’un compteur de C# largeur dans un programme</span><span class="sxs-lookup"><span data-stu-id="689e0-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="689e0-110">La multiplication des `X` contrôlées agissant sur un total de 5 qubits allouera 2 qubits accessoires et sa largeur d’entrée sera de 5.</span><span class="sxs-lookup"><span data-stu-id="689e0-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="689e0-111">Pour vérifier que c’est le cas, nous pouvons utiliser le programme C# suivant :</span><span class="sxs-lookup"><span data-stu-id="689e0-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="689e0-112">La première partie du programme exécute `ApplyMultiControlledX`.</span><span class="sxs-lookup"><span data-stu-id="689e0-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="689e0-113">Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître le nombre de qubits alloués, ainsi que le nombre de qubits qui ont contrôlé `X` reçu en entrée.</span><span class="sxs-lookup"><span data-stu-id="689e0-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="689e0-114">Enfin, pour générer toutes les statistiques collectées par le compteur de largeur au format CSV, nous pouvons utiliser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="689e0-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="689e0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="689e0-115">See also</span></span> ##

- <span data-ttu-id="689e0-116">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="689e0-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
