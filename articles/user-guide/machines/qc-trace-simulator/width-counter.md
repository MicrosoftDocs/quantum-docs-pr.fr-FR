---
title: Compteur de largeur
description: Découvrez le compteur Microsoft QDK Width, qui compte le nombre de qubits alloués et empruntés par chaque opération dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274894"
---
# <a name="width-counter"></a><span data-ttu-id="e4f9e-103">Compteur de largeur</span><span class="sxs-lookup"><span data-stu-id="e4f9e-103">Width Counter</span></span>

<span data-ttu-id="e4f9e-104">Le `Width Counter` compte le nombre d’qubits alloués et empruntés par chaque opération.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="e4f9e-105">Toutes les opérations de l' `Microsoft.Quantum.Intrinsic` espace de noms sont exprimées en termes de rotations qubit uniques, de portes T, de portes qubit Clifford simples, de portes cnotin et de mesures de plusieurs qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="e4f9e-106">Certaines opérations primitives peuvent allouer des qubits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="e4f9e-107">Par exemple, multiplier les `X` portes contrôlées ou les portes contrôlées `T` .</span><span class="sxs-lookup"><span data-stu-id="e4f9e-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="e4f9e-108">Nous allons calculer le nombre de qubits supplémentaires alloués par l’implémentation d’une porte gérée par multiplication `X` :</span><span class="sxs-lookup"><span data-stu-id="e4f9e-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="e4f9e-109">Utilisation d’un compteur de largeur dans un programme C#</span><span class="sxs-lookup"><span data-stu-id="e4f9e-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="e4f9e-110">La multiplication contrôlée `X` agissant sur un total de 5 qubits allouera 2 qubits accessoires et sa largeur d’entrée sera de 5.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="e4f9e-111">Pour vérifier que c’est le cas, nous pouvons utiliser le programme C# suivant :</span><span class="sxs-lookup"><span data-stu-id="e4f9e-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="e4f9e-112">La première partie du programme s’exécute `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="e4f9e-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="e4f9e-113">Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître le nombre d’qubits alloués, ainsi que le nombre de qubits qui `X` ont été contrôlés comme entrée.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="e4f9e-114">Enfin, pour générer toutes les statistiques collectées par le compteur de largeur au format CSV, nous pouvons utiliser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e4f9e-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="e4f9e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4f9e-115">See also</span></span> ##

- <span data-ttu-id="e4f9e-116">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="e4f9e-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>