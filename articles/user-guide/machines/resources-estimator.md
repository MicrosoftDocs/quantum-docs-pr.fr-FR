---
title: Estimation des ressources de Quantum-Kit de développement quantique
description: Découvrez l’estimateur des ressources Microsoft QDK, qui estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604641"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="64254-103">Estimation des ressources du kit de développement quantique (QDK)</span><span class="sxs-lookup"><span data-stu-id="64254-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="64254-104">Comme son nom l’indique, la `ResourcesEstimator` classe estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="64254-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="64254-105">Pour ce faire, il exécute l’opération Quantum sans simuler réellement l’état d’un ordinateur quantique. pour cette raison, elle estime les ressources pour les Q# opérations qui utilisent des milliers de qubits, à condition que la partie classique du code s’exécute dans un délai raisonnable.</span><span class="sxs-lookup"><span data-stu-id="64254-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="64254-106">L’estimateur de ressources s’appuie sur le [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), qui fournit un ensemble plus riche de métriques et d’outils pour déboguer les Q# programmes.</span><span class="sxs-lookup"><span data-stu-id="64254-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="64254-107">Appel et exécution de l’estimateur de ressources</span><span class="sxs-lookup"><span data-stu-id="64254-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="64254-108">Vous pouvez utiliser l’estimateur de ressources pour exécuter toute Q# opération.</span><span class="sxs-lookup"><span data-stu-id="64254-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="64254-109">Pour plus d’informations, consultez [méthodes d’exécution d’un Q# programme](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="64254-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="64254-110">Appel de l’estimateur de ressources à partir de C #</span><span class="sxs-lookup"><span data-stu-id="64254-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="64254-111">Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `ResourcesEstimator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.</span><span class="sxs-lookup"><span data-stu-id="64254-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="64254-112">Notez que, contrairement à la classe `QuantumSimulator`, la classe `ResourcesEstimator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="64254-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="64254-113">Comme le montre l’exemple, `ResourcesEstimator` fournit la `ToTSV()` méthode, qui génère une table avec des valeurs séparées par des tabulations (TSV).</span><span class="sxs-lookup"><span data-stu-id="64254-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="64254-114">Vous pouvez enregistrer la table dans un fichier ou l’afficher dans la console pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="64254-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="64254-115">Voici un exemple de sortie du programme précédent :</span><span class="sxs-lookup"><span data-stu-id="64254-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="64254-116">Une `ResourcesEstimator` instance ne réinitialise pas ses calculs à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="64254-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="64254-117">Si vous utilisez la même instance pour exécuter une autre opération, elle agrège les nouveaux résultats avec les résultats existants.</span><span class="sxs-lookup"><span data-stu-id="64254-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="64254-118">Si vous devez réinitialiser les calculs entre les exécutions, créez une nouvelle instance pour chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="64254-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="64254-119">Appel de l’estimateur de ressources à partir de Python</span><span class="sxs-lookup"><span data-stu-id="64254-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="64254-120">Utilisez la méthode [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) à partir de la bibliothèque Python avec l’opération importée Q# :</span><span class="sxs-lookup"><span data-stu-id="64254-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="64254-121">Appel de l’estimateur de ressources à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="64254-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="64254-122">Quand vous exécutez un Q# programme à partir de la ligne de commande, utilisez le paramètre **--simulateur** (ou **-s** raccourci) pour spécifier l' `ResourcesEstimator` ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="64254-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="64254-123">La commande suivante exécute un programme à l’aide de l’estimateur de ressources :</span><span class="sxs-lookup"><span data-stu-id="64254-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="64254-124">Appel de l’estimateur de ressources des blocs-notes Juptyer</span><span class="sxs-lookup"><span data-stu-id="64254-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="64254-125">Utilisez la Q# commande magique [% estimation](xref:microsoft.quantum.iqsharp.magic-ref.simulate) pour exécuter l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="64254-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="64254-126">Récupération par programmation des données estimées</span><span class="sxs-lookup"><span data-stu-id="64254-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="64254-127">En plus d’une table TSV, vous pouvez récupérer par programmation les ressources estimées lors de l’exécution via la `Data` propriété de l’estimateur de ressources.</span><span class="sxs-lookup"><span data-stu-id="64254-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="64254-128">La `Data` propriété fournit une `System.DataTable` instance de avec deux colonnes : `Metric` et `Sum` , indexées par les noms de métriques.</span><span class="sxs-lookup"><span data-stu-id="64254-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="64254-129">Le code suivant montre comment récupérer et imprimer le nombre total d' `QubitClifford` opérations, `T` et `CNOT` utilisées par une Q# opération :</span><span class="sxs-lookup"><span data-stu-id="64254-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="64254-130">Métriques signalées</span><span class="sxs-lookup"><span data-stu-id="64254-130">Metrics Reported</span></span>

<span data-ttu-id="64254-131">L’estimateur de ressources effectue le suivi des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="64254-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="64254-132">Métrique</span><span class="sxs-lookup"><span data-stu-id="64254-132">Metric</span></span>|<span data-ttu-id="64254-133">Description</span><span class="sxs-lookup"><span data-stu-id="64254-133">Description</span></span>|
|----|----|
|<span data-ttu-id="64254-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="64254-134">__CNOT__</span></span>    |<span data-ttu-id="64254-135">Nombre d’exécutions d' `CNOT` opérations (également appelées opérations Pauli X contrôlées).</span><span class="sxs-lookup"><span data-stu-id="64254-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="64254-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="64254-136">__QubitClifford__</span></span> |<span data-ttu-id="64254-137">Nombre d’exécutions d’opérations qubit Clifford et Pauli uniques.</span><span class="sxs-lookup"><span data-stu-id="64254-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="64254-138">__Mesure__</span><span class="sxs-lookup"><span data-stu-id="64254-138">__Measure__</span></span>    |<span data-ttu-id="64254-139">Nombre d’exécutions de mesures.</span><span class="sxs-lookup"><span data-stu-id="64254-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="64254-140">__R__</span><span class="sxs-lookup"><span data-stu-id="64254-140">__R__</span></span>    |<span data-ttu-id="64254-141">Nombre d’exécutions de rotations à qubit unique, à l’exception des `T` opérations Clifford et Pauli.</span><span class="sxs-lookup"><span data-stu-id="64254-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="64254-142">__T__</span><span class="sxs-lookup"><span data-stu-id="64254-142">__T__</span></span>    |<span data-ttu-id="64254-143">Nombre d’exécutions d' `T` opérations et de leurs conjugués, y compris les `T` opérations, T_x = H. T. H et T_y = Hy. t. hy.</span><span class="sxs-lookup"><span data-stu-id="64254-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="64254-144">__Profondeur__</span><span class="sxs-lookup"><span data-stu-id="64254-144">__Depth__</span></span>|<span data-ttu-id="64254-145">Profondeur du circuit Quantum exécuté par l' Q# opération (voir [ci-dessous](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="64254-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="64254-146">Par défaut, la mesure de profondeur compte uniquement les `T` portes.</span><span class="sxs-lookup"><span data-stu-id="64254-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="64254-147">Pour plus d’informations, consultez [compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="64254-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="64254-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="64254-148">__Width__</span></span>|<span data-ttu-id="64254-149">Largeur du circuit Quantum exécutée par l' Q# opération (voir [ci-dessous](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="64254-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="64254-150">Par défaut, la mesure de profondeur compte uniquement les `T` portes.</span><span class="sxs-lookup"><span data-stu-id="64254-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="64254-151">Pour plus d’informations, consultez [compteur de largeur](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="64254-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="64254-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="64254-152">__QubitCount__</span></span>    |<span data-ttu-id="64254-153">Limite inférieure pour le nombre maximal de qubits allouées pendant l’exécution de l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="64254-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="64254-154">Cette métrique peut ne pas être compatible avec la __profondeur__ (voir ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="64254-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="64254-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="64254-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="64254-156">Nombre maximal de qubits empruntés dans l' Q# opération.</span><span class="sxs-lookup"><span data-stu-id="64254-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="64254-157">Profondeur, largeur et QubitCount</span><span class="sxs-lookup"><span data-stu-id="64254-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="64254-158">Les estimations de profondeur et de largeur signalées sont compatibles les unes avec les autres.</span><span class="sxs-lookup"><span data-stu-id="64254-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="64254-159">(Auparavant, les deux nombres étaient réalisables, mais différents circuits seraient requis pour la profondeur et la largeur.) À l’heure actuelle, les deux métriques de cette paire peuvent être obtenues simultanément par le même circuit.</span><span class="sxs-lookup"><span data-stu-id="64254-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="64254-160">Les métriques suivantes sont signalées :</span><span class="sxs-lookup"><span data-stu-id="64254-160">The following metrics are reported:</span></span>

<span data-ttu-id="64254-161">__Profondeur :__ Pour l’opération racine, le temps nécessaire à l’exécution de celle-ci en supposant des durées de la porte.</span><span class="sxs-lookup"><span data-stu-id="64254-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="64254-162">Pour les opérations appelées ou opérations ultérieures, différence de temps entre le dernier temps de disponibilité de qubit au début et la fin de l’opération.</span><span class="sxs-lookup"><span data-stu-id="64254-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="64254-163">__Largeur :__ Pour l’opération racine : nombre de qubits réellement utilisés pour l’exécuter (et l’opération qu’il appelle).</span><span class="sxs-lookup"><span data-stu-id="64254-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="64254-164">Pour les opérations appelées ou opérations suivantes : combien d’qubits ont été utilisées en plus de la qubits déjà utilisée au début de l’opération.</span><span class="sxs-lookup"><span data-stu-id="64254-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="64254-165">Veuillez noter que les qubits réutilisés ne contribuent pas à ce numéro.</span><span class="sxs-lookup"><span data-stu-id="64254-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="64254-166">Autrement dit, si quelques qubitss ont été libérés avant le début de l’opération A, et que tous les qubit demandés par cette opération A (et les opérations appelées à partir de) ont été satisfaites en réutilisant la version antérieure de qubits, la largeur de l’opération A est indiquée comme étant égale à 0.</span><span class="sxs-lookup"><span data-stu-id="64254-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="64254-167">Les qubits empruntés avec succès ne contribuent pas non plus à la largeur.</span><span class="sxs-lookup"><span data-stu-id="64254-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="64254-168">__QubitCount :__ Pour l’opération racine-nombre minimal de qubits qui seraient suffisants pour exécuter cette opération (et les opérations appelées à partir de celle-ci).</span><span class="sxs-lookup"><span data-stu-id="64254-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="64254-169">Pour les opérations appelées ou opérations suivantes-nombre minimal de qubits qui seraient suffisants pour exécuter cette opération séparément.</span><span class="sxs-lookup"><span data-stu-id="64254-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="64254-170">Ce nombre n’inclut pas les qubits d’entrée.</span><span class="sxs-lookup"><span data-stu-id="64254-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="64254-171">Il inclut les qubits empruntés.</span><span class="sxs-lookup"><span data-stu-id="64254-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="64254-172">Deux modes d’opération sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64254-172">Two modes of operation are supported.</span></span> <span data-ttu-id="64254-173">Le mode est sélectionné en définissant QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="64254-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="64254-174">__OptimizeDepth = true :__ QubitManager est déconseillé de la réutilisation de qubit et alloue de nouvelles qubit chaque fois qu’un qubit est demandé.</span><span class="sxs-lookup"><span data-stu-id="64254-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="64254-175">La __profondeur__ de l’opération racine devient la profondeur minimale (limite inférieure).</span><span class="sxs-lookup"><span data-stu-id="64254-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="64254-176">La __largeur__ compatible est signalée pour cette profondeur (les deux peuvent être effectuées en même temps).</span><span class="sxs-lookup"><span data-stu-id="64254-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="64254-177">Notez que cette largeur n’est probablement pas optimale en raison de cette profondeur.</span><span class="sxs-lookup"><span data-stu-id="64254-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="64254-178">__QubitCount__ peut être inférieur à la largeur de l’opération racine, car il suppose une réutilisation.</span><span class="sxs-lookup"><span data-stu-id="64254-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="64254-179">__OptimizeDepth = false :__ QubitManager est encouragé à réutiliser qubits et à réutiliser les qubits libérés avant d’en allouer de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="64254-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="64254-180">La __largeur__ de l’opération racine devient la largeur minimale (limite inférieure).</span><span class="sxs-lookup"><span data-stu-id="64254-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="64254-181">Une __profondeur__ compatible est signalée sur laquelle elle peut être obtenue.</span><span class="sxs-lookup"><span data-stu-id="64254-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="64254-182">__QubitCount__ sera identique à la __largeur__ de l’opération racine en supposant qu’il n’y ait pas de emprunt.</span><span class="sxs-lookup"><span data-stu-id="64254-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="64254-183">Calcul de la probabilité des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="64254-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="64254-184">Vous pouvez utiliser <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> à partir de l' <xref:Microsoft.Quantum.Diagnostics> espace de noms pour fournir des informations sur la probabilité attendue d’une opération de mesure.</span><span class="sxs-lookup"><span data-stu-id="64254-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="64254-185">Pour plus d’informations, consultez [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="64254-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="64254-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64254-186">See also</span></span>

- [<span data-ttu-id="64254-187">Simulateur de traces Quantum</span><span class="sxs-lookup"><span data-stu-id="64254-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="64254-188">Simulateur Toffoli quantique</span><span class="sxs-lookup"><span data-stu-id="64254-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="64254-189">Simulateur d’état complet quantique</span><span class="sxs-lookup"><span data-stu-id="64254-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
