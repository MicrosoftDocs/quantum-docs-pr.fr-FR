---
title: Estimation des ressources de Quantum-Kit de développement quantique
description: Découvrez l’estimateur des ressources Microsoft QDK, qui estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868183"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="02d7a-103">Estimation des ressources du kit de développement quantique (QDK)</span><span class="sxs-lookup"><span data-stu-id="02d7a-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="02d7a-104">Comme son nom l’indique, la `ResourcesEstimator` classe estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="02d7a-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="02d7a-105">Pour ce faire, il exécute l’opération Quantum sans simuler réellement l’état d’un ordinateur quantique. pour cette raison, elle estime les ressources pour les Q# opérations qui utilisent des milliers de qubits, à condition que la partie classique du code s’exécute dans un délai raisonnable.</span><span class="sxs-lookup"><span data-stu-id="02d7a-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="02d7a-106">L’estimateur de ressources s’appuie sur le [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), qui fournit un ensemble plus riche de métriques et d’outils pour déboguer les Q# programmes.</span><span class="sxs-lookup"><span data-stu-id="02d7a-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="02d7a-107">Appel et exécution de l’estimateur de ressources</span><span class="sxs-lookup"><span data-stu-id="02d7a-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="02d7a-108">Vous pouvez utiliser l’estimateur de ressources pour exécuter toute Q# opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="02d7a-109">Pour plus d’informations, consultez [méthodes d’exécution d’un Q# programme](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="02d7a-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="02d7a-110">Appel de l’estimateur de ressources à partir de C #</span><span class="sxs-lookup"><span data-stu-id="02d7a-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="02d7a-111">Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `ResourceEstimator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="02d7a-112">Notez que, contrairement à la classe `QuantumSimulator`, la classe `ResourceEstimator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="02d7a-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="02d7a-113">Comme le montre l’exemple, `ResourcesEstimator` fournit la `ToTSV()` méthode, qui génère une table avec des valeurs séparées par des tabulations (TSV).</span><span class="sxs-lookup"><span data-stu-id="02d7a-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="02d7a-114">Vous pouvez enregistrer la table dans un fichier ou l’afficher dans la console pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="02d7a-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="02d7a-115">Voici un exemple de sortie du programme précédent :</span><span class="sxs-lookup"><span data-stu-id="02d7a-115">The following is a sample output from the preceding program:</span></span>

```output
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
> <span data-ttu-id="02d7a-116">Une `ResourcesEstimator` instance ne réinitialise pas ses calculs à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="02d7a-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="02d7a-117">Si vous utilisez la même instance pour exécuter une autre opération, elle agrège les nouveaux résultats avec les résultats existants.</span><span class="sxs-lookup"><span data-stu-id="02d7a-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="02d7a-118">Si vous devez réinitialiser les calculs entre les exécutions, créez une nouvelle instance pour chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="02d7a-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="02d7a-119">Appel de l’estimateur de ressources à partir de Python</span><span class="sxs-lookup"><span data-stu-id="02d7a-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="02d7a-120">Utilisez la méthode [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) à partir de la bibliothèque Python avec l’opération importée Q# :</span><span class="sxs-lookup"><span data-stu-id="02d7a-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="02d7a-121">Appel de l’estimateur de ressources à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="02d7a-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="02d7a-122">Quand vous exécutez un Q# programme à partir de la ligne de commande, utilisez le paramètre **--simulateur** (ou **-s** raccourci) pour spécifier l' `ResourcesEstimator` ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="02d7a-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="02d7a-123">La commande suivante exécute un programme à l’aide de l’estimateur de ressources :</span><span class="sxs-lookup"><span data-stu-id="02d7a-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="02d7a-124">Appel de l’estimateur de ressources des blocs-notes Juptyer</span><span class="sxs-lookup"><span data-stu-id="02d7a-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="02d7a-125">Utilisez la Q# commande magique [% estimation](xref:microsoft.quantum.iqsharp.magic-ref.simulate) pour exécuter l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="02d7a-126">Récupération par programmation des données estimées</span><span class="sxs-lookup"><span data-stu-id="02d7a-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="02d7a-127">En plus d’une table TSV, vous pouvez récupérer par programmation les ressources estimées lors de l’exécution via la `Data` propriété de l’estimateur de ressources.</span><span class="sxs-lookup"><span data-stu-id="02d7a-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="02d7a-128">La `Data` propriété fournit une `System.DataTable` instance de avec deux colonnes : `Metric` et `Sum` , indexées par les noms de métriques.</span><span class="sxs-lookup"><span data-stu-id="02d7a-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="02d7a-129">Le code suivant montre comment récupérer et imprimer le nombre total d' `QubitClifford` opérations, `T` et `CNOT` utilisées par une Q# opération :</span><span class="sxs-lookup"><span data-stu-id="02d7a-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="02d7a-130">Métriques signalées</span><span class="sxs-lookup"><span data-stu-id="02d7a-130">Metrics Reported</span></span>

<span data-ttu-id="02d7a-131">L’estimateur de ressources effectue le suivi des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="02d7a-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="02d7a-132">Métrique</span><span class="sxs-lookup"><span data-stu-id="02d7a-132">Metric</span></span>|<span data-ttu-id="02d7a-133">Description</span><span class="sxs-lookup"><span data-stu-id="02d7a-133">Description</span></span>|
|----|----|
|<span data-ttu-id="02d7a-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="02d7a-134">__CNOT__</span></span>    |<span data-ttu-id="02d7a-135">Nombre d’exécutions d' `CNOT` opérations (également appelées opérations Pauli X contrôlées).</span><span class="sxs-lookup"><span data-stu-id="02d7a-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="02d7a-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="02d7a-136">__QubitClifford__</span></span> |<span data-ttu-id="02d7a-137">Nombre d’exécutions d’opérations qubit Clifford et Pauli uniques.</span><span class="sxs-lookup"><span data-stu-id="02d7a-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="02d7a-138">__mesure__</span><span class="sxs-lookup"><span data-stu-id="02d7a-138">__Measure__</span></span>    |<span data-ttu-id="02d7a-139">Nombre d’exécutions de mesures.</span><span class="sxs-lookup"><span data-stu-id="02d7a-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="02d7a-140">__R__</span><span class="sxs-lookup"><span data-stu-id="02d7a-140">__R__</span></span>    |<span data-ttu-id="02d7a-141">Nombre d’exécutions de rotations à qubit unique, à l’exception des `T` opérations Clifford et Pauli.</span><span class="sxs-lookup"><span data-stu-id="02d7a-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="02d7a-142">__T__</span><span class="sxs-lookup"><span data-stu-id="02d7a-142">__T__</span></span>    |<span data-ttu-id="02d7a-143">Nombre d’exécutions d' `T` opérations et de leurs conjugués, y compris les `T` opérations, T_x = H. T. H et T_y = Hy. t. hy.</span><span class="sxs-lookup"><span data-stu-id="02d7a-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="02d7a-144">__Profondeur__</span><span class="sxs-lookup"><span data-stu-id="02d7a-144">__Depth__</span></span>|<span data-ttu-id="02d7a-145">Limite inférieure de la profondeur du circuit Quantum exécutée par l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="02d7a-146">Par défaut, la mesure de profondeur compte uniquement les `T` portes.</span><span class="sxs-lookup"><span data-stu-id="02d7a-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="02d7a-147">Pour plus d’informations, consultez [compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="02d7a-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="02d7a-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="02d7a-148">__Width__</span></span>    |<span data-ttu-id="02d7a-149">Limite inférieure pour le nombre maximal de qubits allouées pendant l’exécution de l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="02d7a-150">Il se peut qu’il ne soit pas possible d’atteindre simultanément les limites inférieures de __profondeur__ et de __largeur__ .</span><span class="sxs-lookup"><span data-stu-id="02d7a-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="02d7a-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="02d7a-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="02d7a-152">Nombre maximal de qubits empruntés dans l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="02d7a-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="02d7a-153">Calcul de la probabilité des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="02d7a-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="02d7a-154">Vous pouvez utiliser <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> à partir de l' <xref:microsoft.quantum.diagnostics> espace de noms pour fournir des informations sur la probabilité attendue d’une opération de mesure.</span><span class="sxs-lookup"><span data-stu-id="02d7a-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="02d7a-155">Pour plus d’informations, consultez [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="02d7a-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="02d7a-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02d7a-156">See also</span></span>

- [<span data-ttu-id="02d7a-157">Simulateur de traces Quantum</span><span class="sxs-lookup"><span data-stu-id="02d7a-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="02d7a-158">Simulateur Toffoli quantique</span><span class="sxs-lookup"><span data-stu-id="02d7a-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="02d7a-159">Simulateur d’état complet quantique</span><span class="sxs-lookup"><span data-stu-id="02d7a-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 