---
title: Estimateur des ressources du kit de développement Quantum
description: 'En savoir plus sur l’estimateur de ressources, qui estime les ressources requises pour exécuter une instance donnée d’une opération Q # sur un ordinateur Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415253"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="795a1-103">Ordinateur cible de l’estimateur de ressources</span><span class="sxs-lookup"><span data-stu-id="795a1-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="795a1-104">Comme son nom l’indique, le `ResourcesEstimator` estime les ressources requises pour exécuter une instance donnée d’une opération Q # sur un ordinateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="795a1-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="795a1-105">Pour ce faire, il exécute l’opération Quantum sans simuler réellement l’état d’un ordinateur quantique. pour cette raison, il peut estimer des ressources pour les opérations Q # qui utilisent des milliers de qubits, si la partie classique du code peut être exécutée dans un délai raisonnable.</span><span class="sxs-lookup"><span data-stu-id="795a1-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="795a1-106">Usage</span><span class="sxs-lookup"><span data-stu-id="795a1-106">Usage</span></span>

<span data-ttu-id="795a1-107">Le `ResourcesEstimator` n’est qu’un autre type d’ordinateur cible. il peut donc être utilisé pour exécuter n’importe quelle opération Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="795a1-108">Comme les autres ordinateurs cibles, pour l’utiliser sur un programme hôte C#, créez une instance et transmettez-la en tant que premier paramètre de la méthode de l’opération `Run` :</span><span class="sxs-lookup"><span data-stu-id="795a1-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="795a1-109">Comme le montre l’exemple, le `ResourcesEstimator` fournit une `ToTSV()` méthode pour générer une table avec des valeurs séparées par des tabulations (TSV) qui peuvent être enregistrées dans un fichier ou écrites dans la console pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="795a1-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="795a1-110">La sortie du programme ci-dessus doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="795a1-110">The output of the above program should look something like this:</span></span>

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="795a1-111">Le `ResourcesEstimator` ne réinitialise pas ses calculs à chaque exécution, si la même instance est utilisée pour exécuter une autre opération, il conserve le nombre d’agrégations en plus des résultats existants.</span><span class="sxs-lookup"><span data-stu-id="795a1-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="795a1-112">Si vous devez réinitialiser les calculs entre les exécutions, créez une nouvelle instance pour chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="795a1-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="795a1-113">Récupération par programmation des données estimées</span><span class="sxs-lookup"><span data-stu-id="795a1-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="795a1-114">En plus d’une table TSV, les ressources estimées peuvent être récupérées par programme par le biais de la `ResourcesEstimator` `Data` propriété de.</span><span class="sxs-lookup"><span data-stu-id="795a1-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="795a1-115">`Data`fournit une `System.DataTable` instance de avec deux colonnes : `Metric` et `Sum` , indexées par les noms de métriques.</span><span class="sxs-lookup"><span data-stu-id="795a1-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="795a1-116">Le code suivant montre comment récupérer et imprimer le nombre total de `QubitClifford` , `T` ainsi que les `CNOT` portes utilisées par une opération Q # :</span><span class="sxs-lookup"><span data-stu-id="795a1-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="795a1-117">Métriques signalées</span><span class="sxs-lookup"><span data-stu-id="795a1-117">Metrics Reported</span></span>

<span data-ttu-id="795a1-118">Voici la liste des métriques estimées par `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="795a1-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="795a1-119">__Cnotin__: le nombre de portes cnotin (également appelées portes Pauli X contrôlées) exécutées.</span><span class="sxs-lookup"><span data-stu-id="795a1-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="795a1-120">__QubitClifford__: nombre de toutes les passerelles qubit Clifford et Pauli exécutées.</span><span class="sxs-lookup"><span data-stu-id="795a1-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="795a1-121">__Mesure__: nombre de mesures exécutées.</span><span class="sxs-lookup"><span data-stu-id="795a1-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="795a1-122">__R__: nombre de rotations qubit uniques exécutées, à l’exception des portes T, Clifford et Pauli.</span><span class="sxs-lookup"><span data-stu-id="795a1-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="795a1-123">__T__: le nombre de portes t et leurs conjugués, y compris la porte t, T_x = H. T. H et T_y = Hy. t. HY, exécutés.</span><span class="sxs-lookup"><span data-stu-id="795a1-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="795a1-124">__Depth__: limite inférieure de la profondeur du circuit Quantum exécutée par l’opération Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-124">__Depth__: The lower bound for the depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="795a1-125">Par défaut, seules les portes T sont comptées en profondeur. pour plus d’informations, consultez [compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="795a1-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="795a1-126">__Width__: limite inférieure pour le nombre maximal de qubits alloués lors de l’exécution de l’opération Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-126">__Width__: The lower bound for the maximum number of qubits allocated during the execution of the Q# operation.</span></span> <span data-ttu-id="795a1-127">Il se peut qu’il ne soit pas possible d’atteindre simultanément les limites inférieures de __profondeur__ et de __largeur__ .</span><span class="sxs-lookup"><span data-stu-id="795a1-127">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>
* <span data-ttu-id="795a1-128">__BorrowedWidth__: nombre maximal de qubits empruntés à l’intérieur de l’opération Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-128">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="795a1-129">Génération de la probabilité des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="795a1-129">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="795a1-130"><xref:microsoft.quantum.intrinsic.assertprob>à partir de l' <xref:microsoft.quantum.intrinsic> espace de noms peut être utilisé pour fournir des informations sur la probabilité attendue d’une mesure pour aider à piloter l’exécution du programme Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-130"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="795a1-131">L'exemple suivant illustre ce mécanisme :</span><span class="sxs-lookup"><span data-stu-id="795a1-131">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="795a1-132">Quand le `ResourcesEstimator` rencontre, `AssertProb` il enregistre cette mesure `PauliZ` sur `source` et `q` doit recevoir un résultat de `Zero` avec une probabilité de 0,5.</span><span class="sxs-lookup"><span data-stu-id="795a1-132">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="795a1-133">Lorsqu’il est exécuté `M` ultérieurement, il trouve les valeurs enregistrées des probabilités de résultat et `M` retourne `Zero` ou avec la `One` probabilité 0,5.</span><span class="sxs-lookup"><span data-stu-id="795a1-133">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="795a1-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="795a1-134">See also</span></span>

<span data-ttu-id="795a1-135">Le `ResourcesEstimator` repose sur le [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace, qui fournit un ensemble plus riche de métriques, la possibilité de rapporter des métriques sur le graphique d’appel complet et des fonctionnalités telles que l' [outil de vérification des entrées distinctes](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) pour faciliter la détection des bogues sur les programmes Q #.</span><span class="sxs-lookup"><span data-stu-id="795a1-135">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="795a1-136">Pour plus d’informations, consultez la documentation de [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="795a1-136">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>
