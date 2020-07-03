---
title: 'Méthodes d’exécution d’un programme Q #'
description: 'Vue d’ensemble des différentes façons d’exécuter les programmes Q #. À partir de la ligne de commande, des bloc-notes Q # Jupyter et des programmes hôtes classiques en Python ou en langage .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887684"
---
# <a name="ways-to-run-a-q-program"></a><span data-ttu-id="21360-104">Méthodes d’exécution d’un programme Q #</span><span class="sxs-lookup"><span data-stu-id="21360-104">Ways to run a Q# program</span></span>

<span data-ttu-id="21360-105">L’un des principaux atouts du kit de développement Quantum est sa flexibilité sur les plateformes et les environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="21360-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="21360-106">Toutefois, cela signifie également que les nouveaux utilisateurs Q # peuvent être déconcertés ou submergés par les nombreuses options figurant dans le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="21360-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="21360-107">Sur cette page, nous expliquons ce qui se passe quand un programme Q # est exécuté et que vous comparez les différentes façons dont les utilisateurs peuvent le faire.</span><span class="sxs-lookup"><span data-stu-id="21360-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="21360-108">Une distinction principale est que Q # peut être exécuté :</span><span class="sxs-lookup"><span data-stu-id="21360-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="21360-109">en tant qu’application autonome, où Q # est le seul langage impliqué et le programme est appelé directement.</span><span class="sxs-lookup"><span data-stu-id="21360-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="21360-110">Deux méthodes appartiennent en fait à cette catégorie :</span><span class="sxs-lookup"><span data-stu-id="21360-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="21360-111">l’interface de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="21360-111">the command line interface</span></span>
  - <span data-ttu-id="21360-112">Notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="21360-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="21360-113">avec un *programme hôte*supplémentaire, écrit en Python ou un langage .net (par exemple, C# ou F #), qui appelle ensuite le programme et peut poursuivre le traitement des résultats retournés.</span><span class="sxs-lookup"><span data-stu-id="21360-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="21360-114">Pour mieux comprendre ces processus et leurs différences, nous considérons un simple programme Q # et voyons comment il peut être exécuté.</span><span class="sxs-lookup"><span data-stu-id="21360-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-q-program"></a><span data-ttu-id="21360-115">Programme Basic Q #</span><span class="sxs-lookup"><span data-stu-id="21360-115">Basic Q# program</span></span>

<span data-ttu-id="21360-116">Un programme Quantum de base peut consister à préparer un qubit dans une superposition égale des États $ \ket {0} $ et $ \ket {1} $, à le mesurer et à retourner le résultat, qui sera, de manière aléatoire, l’un de ces deux États avec une probabilité égale.</span><span class="sxs-lookup"><span data-stu-id="21360-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="21360-117">En effet, ce processus est au cœur du démarrage rapide du [Générateur de nombres aléatoires quantiques](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="21360-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="21360-118">Dans Q #, cette opération est effectuée par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="21360-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="21360-119">Toutefois, ce code seul ne peut pas être exécuté par Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="21360-120">Pour cela, il doit créer le corps d’une [opération](xref:microsoft.quantum.guide.basics#q-operations-and-functions), qui est ensuite exécutée quand elle est appelée---soit directement, soit par une autre opération.</span><span class="sxs-lookup"><span data-stu-id="21360-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="21360-121">Par conséquent, vous pouvez écrire une opération de la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="21360-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="21360-122">Vous avez défini une opération, `MeasureSuperposition` , qui ne prend aucune entrée et retourne une valeur de type [résultat](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="21360-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="21360-123">Alors que les exemples de cette page se composent uniquement d' *opérations*q #, tous les concepts que nous aborderons se rapportent également aux *fonctions*q #, et par conséquent, nous les appelons collectivement *callables*.</span><span class="sxs-lookup"><span data-stu-id="21360-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="21360-124">Leurs différences sont présentées dans la section [notions de base sur Q # : opérations et fonctions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), et plus d’informations sur leur définition se trouvent dans [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="21360-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-q-file"></a><span data-ttu-id="21360-125">Pouvant être appelé dans un fichier Q #</span><span class="sxs-lookup"><span data-stu-id="21360-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="21360-126">L’appelable est précisément ce qui est appelé et exécuté par Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="21360-127">Toutefois, il faut quelques ajouts pour inclure un `*.qs` fichier Q # complet.</span><span class="sxs-lookup"><span data-stu-id="21360-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="21360-128">Tous les types Q # et callables (ceux que vous définissez et ceux qui sont intrinsèques au langage) sont définis dans des *espaces de noms*, qui fournissent chacun un nom complet qui peut ensuite être référencé.</span><span class="sxs-lookup"><span data-stu-id="21360-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="21360-129">Par exemple, les [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) opérations et se trouvent dans les [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) espaces de noms et (qui font partie des [bibliothèques standard Q #](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="21360-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="21360-130">En tant que tels, ils peuvent toujours être appelés par le biais de leurs noms *complets* `Microsoft.Quantum.Intrinsic.H(<qubit>)` et `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , mais le fait de toujours effectuer cela entraînerait un code très encombré.</span><span class="sxs-lookup"><span data-stu-id="21360-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="21360-131">Au lieu de cela, `open` les instructions permettent de référencer callables avec un raccourci plus concis, comme nous l’avons fait dans le corps de l’opération ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="21360-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="21360-132">Le fichier Q # complet contenant notre opération consiste donc à définir notre propre espace de noms, à ouvrir les espaces de noms pour les callables utilisés par notre opération, puis à exécuter l’opération suivante :</span><span class="sxs-lookup"><span data-stu-id="21360-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="21360-133">Les espaces de noms peuvent également être dotés d’un *alias* lorsqu’ils sont ouverts, ce qui peut être utile si les noms d’appel/type dans deux espaces de noms sont en conflit.</span><span class="sxs-lookup"><span data-stu-id="21360-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="21360-134">Par exemple, nous pourrions utiliser à la place `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ci-dessus, puis appeler `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="21360-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="21360-135">La seule exception est l' [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) espace de noms, qui est toujours ouvert automatiquement.</span><span class="sxs-lookup"><span data-stu-id="21360-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="21360-136">Par conséquent, callables [`Length`](xref:microsoft.quantum.core.length) peut toujours être utilisé directement.</span><span class="sxs-lookup"><span data-stu-id="21360-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="21360-137">Exécution sur les ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="21360-137">Execution on target machines</span></span>

<span data-ttu-id="21360-138">À présent, le modèle d’exécution générale d’un programme Q # devient clair.</span><span class="sxs-lookup"><span data-stu-id="21360-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="21360-139">Tout d’abord, l’appel spécifique à exécuter a accès à tout autre callables et à tous les types définis dans le même espace de noms.</span><span class="sxs-lookup"><span data-stu-id="21360-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="21360-140">Elle y accède également à partir de l’une des [bibliothèques Q #](xref:microsoft.quantum.libraries), mais celles-ci doivent être référencées par le biais de leur nom complet ou de l’utilisation d' `open` instructions décrites ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="21360-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="21360-141">L’appel à lui-même est ensuite exécuté sur un *[ordinateur cible](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="21360-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="21360-142">Ces machines cibles peuvent être du matériel Quantum réel ou des simulateurs multiples disponibles dans le cadre du QDK.</span><span class="sxs-lookup"><span data-stu-id="21360-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="21360-143">Dans notre cas, la machine cible la plus utile est une instance du [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , qui calcule le comportement du programme comme s’il était exécuté sur un ordinateur quantique sans bruit.</span><span class="sxs-lookup"><span data-stu-id="21360-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="21360-144">Jusqu’à présent, nous avons décrit ce qui se produit lorsqu’un appel Q # spécifique est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="21360-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="21360-145">Même si Q # est utilisé dans une application autonome ou avec un programme hôte, ce processus général est plus ou moins le même---donc la flexibilité de QDK.</span><span class="sxs-lookup"><span data-stu-id="21360-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="21360-146">Les différences entre les différentes façons d’appeler dans le kit de développement Quantum s’affichent dans la *manière dont* Q # Callable est appelé pour être exécuté, et de quelle manière les résultats sont retournés.</span><span class="sxs-lookup"><span data-stu-id="21360-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="21360-147">Plus précisément, les différences tournent autour</span><span class="sxs-lookup"><span data-stu-id="21360-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="21360-148">indiquant quel Q # Callable doit être exécuté,</span><span class="sxs-lookup"><span data-stu-id="21360-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="21360-149">Comment les arguments pouvant être appelés peuvent être fournis,</span><span class="sxs-lookup"><span data-stu-id="21360-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="21360-150">spécifiant l’ordinateur cible sur lequel l’exécuter et</span><span class="sxs-lookup"><span data-stu-id="21360-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="21360-151">Comment les résultats sont retournés.</span><span class="sxs-lookup"><span data-stu-id="21360-151">how any results are returned.</span></span>

<span data-ttu-id="21360-152">Tout d’abord, nous expliquons comment cela s’effectue avec l’application autonome Q # à partir de la ligne de commande, puis passez à l’utilisation des programmes hôtes Python et C#.</span><span class="sxs-lookup"><span data-stu-id="21360-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="21360-153">Nous nous réservons l’application autonome des bloc-notes Q # Jupyter pour la dernière version, car contrairement aux trois premières, les fonctionnalités principales ne sont pas centrées autour d’un fichier Q # local.</span><span class="sxs-lookup"><span data-stu-id="21360-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="21360-154">Bien que nous ne les illustrions pas dans ces exemples, l’une des similitudes entre les méthodes d’exécution est que tous les messages imprimés à partir du programme Q # (à l’aide de [`Message`](xref:microsoft.quantum.intrinsic.message) ou [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) , par exemple) sont généralement imprimés sur la console respective.</span><span class="sxs-lookup"><span data-stu-id="21360-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="q-from-the-command-line"></a><span data-ttu-id="21360-155">Q # à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="21360-155">Q# from the command line</span></span>
<span data-ttu-id="21360-156">L’une des méthodes les plus simples pour commencer à écrire des programmes Q # consiste à éviter d’avoir à vous soucier des fichiers distincts et d’un autre langage.</span><span class="sxs-lookup"><span data-stu-id="21360-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="21360-157">L’utilisation de Visual Studio Code ou Visual Studio avec l’extension QDK permet un workflow de travail transparent dans lequel nous exécutons Q # callables à partir d’un seul fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="21360-158">Pour ce faire, nous appellerons finalement l’exécution du programme en entrant</span><span class="sxs-lookup"><span data-stu-id="21360-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="21360-159">dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="21360-159">in the command line.</span></span>
<span data-ttu-id="21360-160">Le flux de travail le plus simple est lorsque l’emplacement du répertoire du terminal est le même que celui du fichier Q #, qui peut être facilement géré avec la modification de fichier Q # en utilisant le terminal intégré dans VS Code, par exemple.</span><span class="sxs-lookup"><span data-stu-id="21360-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="21360-161">Toutefois, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte de nombreuses options et le programme peut également être exécuté à partir d’un emplacement différent en fournissant simplement `--project <PATH>` l’emplacement du fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-q-file"></a><span data-ttu-id="21360-162">Ajouter un point d’entrée au fichier Q #</span><span class="sxs-lookup"><span data-stu-id="21360-162">Add entry point to Q# file</span></span>

<span data-ttu-id="21360-163">La plupart des fichiers Q # contiennent plus d’un appelable, donc naturellement, nous devons laisser le compilateur savoir *quel* appel peut s’exécuter lorsque nous fournissons la `dotnet run` commande.</span><span class="sxs-lookup"><span data-stu-id="21360-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="21360-164">Cela s’effectue par le biais d’une simple modification du fichier Q # lui-même :</span><span class="sxs-lookup"><span data-stu-id="21360-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="21360-165">Ajoutez une ligne qui `@EntryPoint()` précède directement l’appelable.</span><span class="sxs-lookup"><span data-stu-id="21360-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="21360-166">Notre fichier ci-dessus serait donc</span><span class="sxs-lookup"><span data-stu-id="21360-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="21360-167">À présent, un appel de `dotnet run` à partir de la ligne de commande provoque `MeasureSuperposition` l’exécution, et la valeur retournée est ensuite imprimée directement sur le terminal.</span><span class="sxs-lookup"><span data-stu-id="21360-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="21360-168">Par conséquent, vous verrez ou vous pouvez l' `One` `Zero` Imprimer.</span><span class="sxs-lookup"><span data-stu-id="21360-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="21360-169">Notez que cela n’a pas d’importance si vous avez plus de callables défini au-dessous, mais uniquement s' `MeasureSuperposition` exécutera.</span><span class="sxs-lookup"><span data-stu-id="21360-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="21360-170">En outre, ce n’est pas un problème si votre appelable comprend des [Commentaires de documentation](xref:microsoft.quantum.guide.filestructure#documentation-comments) avant sa déclaration, l' `@EntryPoint()` attribut peut être placé juste au-dessus de lui.</span><span class="sxs-lookup"><span data-stu-id="21360-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="21360-171">Arguments pouvant être appelés</span><span class="sxs-lookup"><span data-stu-id="21360-171">Callable arguments</span></span>

<span data-ttu-id="21360-172">Jusqu’à présent, nous avons uniquement considéré une opération qui n’accepte aucune entrée.</span><span class="sxs-lookup"><span data-stu-id="21360-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="21360-173">Supposons que nous voulions effectuer une opération similaire, mais sur plusieurs qubits---le nombre de qui est fourni en tant qu’argument.</span><span class="sxs-lookup"><span data-stu-id="21360-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="21360-174">Une telle opération peut être écrite sous la forme</span><span class="sxs-lookup"><span data-stu-id="21360-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="21360-175">où la valeur retournée est un tableau des résultats de mesure.</span><span class="sxs-lookup"><span data-stu-id="21360-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="21360-176">Notez que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) et [`ForEach`](xref:microsoft.quantum.arrays.foreach) se trouvent dans [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) les [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) espaces de noms et, nécessitant des `open` instructions supplémentaires pour chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="21360-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="21360-177">Si nous déplaçons l' `@EntryPoint()` attribut pour qu’il précède cette nouvelle opération (Notez qu’il ne peut y avoir qu’une seule ligne dans un fichier), tenter de l’exécuter avec `dotnet run` génère simplement un message d’erreur qui indique les options de ligne de commande supplémentaires requises et comment les exprimer.</span><span class="sxs-lookup"><span data-stu-id="21360-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="21360-178">Le format général de la ligne de commande est `dotnet run [options]` en réalité, et les arguments pouvant être appelés sont fournis ici.</span><span class="sxs-lookup"><span data-stu-id="21360-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="21360-179">Dans ce cas, l’argument `n` est manquant et il indique que nous devons fournir l’option `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="21360-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="21360-180">Pour exécuter `MeasureSuperpositionArray` `n=4` qubits, nous utilisons donc</span><span class="sxs-lookup"><span data-stu-id="21360-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="21360-181">produire une sortie similaire à</span><span class="sxs-lookup"><span data-stu-id="21360-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="21360-182">Ce bien évidemment s’étend à plusieurs arguments.</span><span class="sxs-lookup"><span data-stu-id="21360-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="21360-183">Les noms d’arguments définis dans `camelCase` sont légèrement modifiés par le compilateur pour être acceptés en tant qu’entrées Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="21360-184">Par exemple, si au lieu de `n` , nous avons utilisé le nom `numQubits` ci-dessus, cette entrée est fournie dans la ligne de commande via à la `--num-qubits 4` place de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="21360-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="21360-185">Le message d’erreur fournit également d’autres options qui peuvent être utilisées, notamment la modification de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="21360-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="21360-186">Ordinateurs cibles différents</span><span class="sxs-lookup"><span data-stu-id="21360-186">Different target machines</span></span>

<span data-ttu-id="21360-187">Comme les sorties de nos opérations jusqu’à présent ont été les résultats attendus de leur action sur des qubits réels, il est clair que l’ordinateur cible par défaut à partir de la ligne de commande est le simulateur quauntum en état complet, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="21360-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="21360-188">Toutefois, nous pouvons demander à callables de s’exécuter sur un ordinateur cible spécifique avec l’option `--simulator` (ou le raccourci `-s` ).</span><span class="sxs-lookup"><span data-stu-id="21360-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="21360-189">Par exemple, nous pourrions l’exécuter sur [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="21360-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="21360-190">La sortie imprimée est alors</span><span class="sxs-lookup"><span data-stu-id="21360-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="21360-191">Pour plus d’informations sur ce que ces métriques indiquent, consultez [estimation des ressources : mesures signalées](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="21360-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="21360-192">Résumé d’exécution de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="21360-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a><span data-ttu-id="21360-193">Options non-Q # `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="21360-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="21360-194">Comme nous l’avons brièvement mentionné plus haut avec l' `--project` option, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte également des options non liées aux arguments Q # Callable.</span><span class="sxs-lookup"><span data-stu-id="21360-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="21360-195">Si vous fournissez les deux types d’options, les `dotnet` options spécifiques à doivent être fournies en premier, suivies d’un délimiteur, puis des `--` options spécifiques à Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="21360-196">Par exemple, la spécification d’un chemin d’accès avec un nombre qubits pour l’opération ci-dessus est exécutée via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="21360-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="q-with-host-programs"></a><span data-ttu-id="21360-197">Q # avec les programmes hôtes</span><span class="sxs-lookup"><span data-stu-id="21360-197">Q# with host programs</span></span>

<span data-ttu-id="21360-198">Avec notre fichier Q # en main, une alternative à l’appel d’une opération ou d’une fonction directement à partir de la ligne de commande consiste à utiliser un *programme hôte* dans un autre langage classique.</span><span class="sxs-lookup"><span data-stu-id="21360-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="21360-199">Plus précisément, cela peut être fait avec Python ou un langage .NET tel que C# ou F # (par souci de concision, nous allons uniquement détailler C#).</span><span class="sxs-lookup"><span data-stu-id="21360-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="21360-200">Un peu plus de configuration est nécessaire pour activer l’interopérabilité, mais ces informations sont disponibles dans les [guides d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="21360-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="21360-201">Pour résumer, la situation comprend maintenant un fichier programme hôte (par exemple `*.py` ou `*.cs` ) au même emplacement que notre fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="21360-202">C’est maintenant le programme *hôte* qui est exécuté, et au cours de son exécution, il peut appeler des fonctions et des opérations q # spécifiques à partir du fichier q #.</span><span class="sxs-lookup"><span data-stu-id="21360-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="21360-203">Le noyau de l’interopérabilité est basé sur le compilateur Q # qui rend le contenu du fichier Q # accessible au programme hôte afin qu’il puisse être appelé.</span><span class="sxs-lookup"><span data-stu-id="21360-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="21360-204">L’un des principaux avantages de l’utilisation d’un programme hôte est que les données classiques retournées par le programme Q # peuvent ensuite être traitées plus en détail dans le langage hôte.</span><span class="sxs-lookup"><span data-stu-id="21360-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="21360-205">Cela peut consister en un traitement de données avancé (par exemple, un qui ne peut pas être effectué en interne dans Q #), puis à appeler des actions Q # supplémentaires sur la base de ces résultats, ou à des fins aussi simples que le traçage des résultats Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="21360-206">Le schéma général est présenté ici et nous aborderons les implémentations spécifiques de Python et C# ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="21360-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="21360-207">Vous trouverez un exemple d’utilisation d’un programme hôte F # dans les [exemples d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="21360-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="21360-208">L' `@EntryPoint()` attribut utilisé pour les applications de ligne de commande Q # ne peut pas être utilisé avec les programmes hôtes.</span><span class="sxs-lookup"><span data-stu-id="21360-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="21360-209">Une erreur sera déclenchée si elle est présente dans le fichier Q # qui est appelé par un hôte.</span><span class="sxs-lookup"><span data-stu-id="21360-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="21360-210">Pour fonctionner avec différents programmes hôtes, il n’y a aucune modification requise dans un `*.qs` fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="21360-211">Les implémentations de programmes hôtes suivantes fonctionnent toutes avec le même fichier Q # :</span><span class="sxs-lookup"><span data-stu-id="21360-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="21360-212">Sélectionnez l’onglet correspondant à la langue de votre hôte qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="21360-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="21360-213">Python</span><span class="sxs-lookup"><span data-stu-id="21360-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="21360-214">Un programme hôte Python est construit comme suit :</span><span class="sxs-lookup"><span data-stu-id="21360-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="21360-215">Importez le `qsharp` module, qui inscrit le chargeur de module pour l’interopérabilité Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="21360-216">Cela permet aux espaces de noms Q # d’apparaître en tant que modules python, à partir desquels nous pouvons « importer » Q # callables.</span><span class="sxs-lookup"><span data-stu-id="21360-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="21360-217">Notez qu’il ne s’agit techniquement pas des callables Q # qui sont importés, mais plutôt des stubs Python qui permettent de les appeler.</span><span class="sxs-lookup"><span data-stu-id="21360-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="21360-218">Ceux-ci se comportent ensuite comme des objets de classes Python, sur lesquels nous utilisons des méthodes pour spécifier les ordinateurs cibles vers lesquels envoyer l’opération pour l’exécution.</span><span class="sxs-lookup"><span data-stu-id="21360-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="21360-219">Importez ces Q # callables que nous appellerons directement---dans ce cas, `MeasureSuperposition` et `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="21360-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="21360-220">Une fois le `qsharp` module importé, vous pouvez également importer des callables directement à partir des espaces de noms de bibliothèque Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="21360-221">Parmi tout autre code Python, vous pouvez maintenant appeler ces callables sur des ordinateurs cibles spécifiques et leur attribuer des retours à des variables (s’ils retournent une valeur) pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="21360-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="21360-222">Spécification d’ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="21360-222">Specifying target machines</span></span>
<span data-ttu-id="21360-223">L’appel d’une opération à exécuter sur un ordinateur cible spécifique s’effectue à l’aide de différentes méthodes Python sur l’objet importé.</span><span class="sxs-lookup"><span data-stu-id="21360-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="21360-224">Par exemple, `.simulate(<args>)` utilise `QuantumSimulator` pour exécuter l’opération, tandis que le `.estimate_resources(<args>)` fait sur le `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="21360-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="21360-225">Passage d’entrées à Q\#</span><span class="sxs-lookup"><span data-stu-id="21360-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="21360-226">Les arguments pour le Q # Callable doivent être fournis sous la forme d’un argument de mot clé, où le mot clé est le nom de l’argument dans la définition de Q # Callable.</span><span class="sxs-lookup"><span data-stu-id="21360-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="21360-227">Autrement dit, `MeasureSuperpositionArray.simulate(n=4)` est valide, alors qu' `MeasureSuperpositionArray.simulate(4)` une erreur est levée.</span><span class="sxs-lookup"><span data-stu-id="21360-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="21360-228">Par conséquent, le programme hôte python</span><span class="sxs-lookup"><span data-stu-id="21360-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="21360-229">génère une sortie semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="21360-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="21360-230">C#</span><span class="sxs-lookup"><span data-stu-id="21360-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="21360-231">Un programme hôte C# possède plusieurs composants et fonctionne très étroitement avec certains composants du QDK, tels que les simulateurs, qui sont eux-mêmes basés sur C#.</span><span class="sxs-lookup"><span data-stu-id="21360-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="21360-232">Le compilateur Q # fonctionne ici en générant un espace de noms C# nommé de façon équivalente à partir de l’espace de noms Q # dans notre fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="21360-233">Il génère ensuite une classe C# nommée de manière équivalente pour chacun des Q # callables ou types définis dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="21360-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="21360-234">Tout d’abord, nous faisons en sorte que toutes les classes utilisées dans notre programme hôte soient disponibles avec des `using` instructions, qui sont à peu près analogue aux `open` instructions de notre fichier Q # :</span><span class="sxs-lookup"><span data-stu-id="21360-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="21360-235">Ensuite, nous déclarons notre espace de noms C#, quelques autres bits et éléments (consultez le bloc de code complet ci-dessous), puis toute programmation classique que nous aimerions (par exemple, le calcul d’arguments pour le Q # callables).</span><span class="sxs-lookup"><span data-stu-id="21360-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="21360-236">Ce dernier n’est pas nécessaire dans notre cas, mais un exemple d’utilisation de ce type est disponible dans l' [exemple d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="21360-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="21360-237">Ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="21360-237">Target machines</span></span>

<span data-ttu-id="21360-238">En revenons à Q #, nous devons créer une instance de n’importe quelle machine cible sur laquelle nous allons exécuter nos opérations.</span><span class="sxs-lookup"><span data-stu-id="21360-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="21360-239">L’utilisation d’autres ordinateurs cibles est aussi simple que l’instanciation d’un autre ordinateur, bien que la manière de procéder et le traitement des retours puissent être légèrement différents.</span><span class="sxs-lookup"><span data-stu-id="21360-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="21360-240">Par souci de concision, nous nous contenterons pour l' [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) instant, et inclurons les [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [ci-dessous](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="21360-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="21360-241">Chaque classe C# générée à partir des opérations Q # a une `Run` méthode, dont le premier argument doit être l’instance de machine cible.</span><span class="sxs-lookup"><span data-stu-id="21360-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="21360-242">Ainsi, pour exécuter `MeasureSuperposition` sur le `QuantumSimulator` , nous utilisons `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="21360-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="21360-243">Les résultats retournés peuvent ensuite être affectés à des variables en C# :</span><span class="sxs-lookup"><span data-stu-id="21360-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="21360-244">La `Run` méthode est exécutée de façon asynchrone, car ce sera le cas pour le matériel Quantum réel. par conséquent, le `await` mot clé bloque l’exécution jusqu’à ce que la tâche se termine.</span><span class="sxs-lookup"><span data-stu-id="21360-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="21360-245">Si le Q # Callable n’a pas de retour (c’est-à-dire qu’il a un type de retour `Unit` ), l’exécution peut toujours être effectuée de la même manière sans l’assigner à une variable.</span><span class="sxs-lookup"><span data-stu-id="21360-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="21360-246">Dans ce cas, la ligne entière se compose simplement de</span><span class="sxs-lookup"><span data-stu-id="21360-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="21360-247">Arguments</span><span class="sxs-lookup"><span data-stu-id="21360-247">Arguments</span></span>

<span data-ttu-id="21360-248">Les arguments de Q # Callable sont simplement passés en tant qu’arguments supplémentaires après l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="21360-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="21360-249">Par conséquent, les résultats de `MeasureSuperpositionArray` sur `n=4` qubits seraient récupérés via</span><span class="sxs-lookup"><span data-stu-id="21360-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="21360-250">Un programme hôte C# complet peut donc ressembler à</span><span class="sxs-lookup"><span data-stu-id="21360-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="21360-251">À l’emplacement du fichier C#, le programme hôte peut être exécuté à partir de la ligne de commande en entrant</span><span class="sxs-lookup"><span data-stu-id="21360-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="21360-252">dans ce cas, vous verrez une sortie écrite dans la console, similaire à</span><span class="sxs-lookup"><span data-stu-id="21360-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="21360-253">En raison de l’interopérabilité du compilateur avec les espaces de noms, nous pourrions également rendre notre Q # callables disponible sans l' `using NamespaceName;` instruction et en faisant simplement correspondre le titre de l’espace de noms C# à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="21360-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="21360-254">Autrement dit, en remplaçant `namespace host` par `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="21360-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="21360-255">Inclusion de l’estimateur de ressources</span><span class="sxs-lookup"><span data-stu-id="21360-255">Including the resources estimator</span></span>

<span data-ttu-id="21360-256">Le [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requiert une implémentation légèrement différente pour récupérer la sortie.</span><span class="sxs-lookup"><span data-stu-id="21360-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="21360-257">Tout d’abord, au lieu de les instancier en tant que variable avec une `using` instruction (comme nous le faisons avec `QuantumSimulator` ), nous instancions plus directement les objets de la classe via</span><span class="sxs-lookup"><span data-stu-id="21360-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="21360-258">Notez qu’au lieu d’utiliser un simulateur cible unique pour plusieurs opérations Q #, nous avons instancié une pour chaque.</span><span class="sxs-lookup"><span data-stu-id="21360-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="21360-259">Cela est dû au fait que les objets eux-mêmes sont modifiés lorsqu’ils sont utilisés en tant qu’ordinateurs cibles, et que leurs résultats peuvent ensuite être récupérés ultérieurement avec la méthode de classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="21360-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="21360-260">Pour exécuter les opérations sur les estimateurs de ressources, nous utilisons</span><span class="sxs-lookup"><span data-stu-id="21360-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="21360-261">puis, récupérez les résultats sous forme de valeurs séparées par des tabulations (TSV) avec `estimatorSingleQ.ToTSV()` et `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="21360-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="21360-262">Ainsi, un programme hôte C# complet qui utilise à la fois le `QuantumSimulator` et `ResourcesEstimator` peut prendre la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="21360-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="21360-263">ce qui donne une sortie similaire à</span><span class="sxs-lookup"><span data-stu-id="21360-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a><span data-ttu-id="21360-264">Notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="21360-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="21360-265">Q # les blocs-notes Jupyter utilisent le noyau IQ #, qui vous permet de définir, compiler et exécuter Q # callables dans un seul bloc-notes---les instructions, les notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="21360-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="21360-266">Cela signifie que s’il est possible d’importer et d’utiliser le contenu des `*.qs` fichiers Q #, ils ne sont pas nécessaires dans le modèle d’exécution.</span><span class="sxs-lookup"><span data-stu-id="21360-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="21360-267">Ici, nous allons expliquer en détail comment exécuter les opérations Q # définies ci-dessus, mais une introduction plus étendue à l’utilisation des Notebooks Q # Jupyter est fournie à l' [Introduction aux notebooks q # et Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="21360-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="21360-268">Définition des opérations</span><span class="sxs-lookup"><span data-stu-id="21360-268">Defining operations</span></span>

<span data-ttu-id="21360-269">Dans un Jupyter Notebook Q #, vous entrez le code Q # comme nous le ferions à l’intérieur de l’espace de noms d’un fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="21360-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="21360-270">Nous pouvons donc activer l’accès à callables à partir des [bibliothèques standard Q #](xref:microsoft.quantum.qsharplibintro) avec des `open` instructions pour leurs espaces de noms respectifs.</span><span class="sxs-lookup"><span data-stu-id="21360-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="21360-271">Lors de l’exécution d’une cellule avec une telle instruction, les définitions de ces espaces de noms sont disponibles dans l’ensemble de l’espace de travail.</span><span class="sxs-lookup"><span data-stu-id="21360-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="21360-272">Callables de [Microsoft. Quantum. Intrinsic](xref:microsoft.quantum.intrinsic) et [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (par exemple [`H`](xref:microsoft.quantum.intrinsic.h) , et [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) sont automatiquement disponibles pour les opérations définies dans les cellules des blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="21360-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="21360-273">Toutefois, cela n’est pas vrai pour le code provenant de fichiers sources Q # externes (processus présenté dans [Introduction aux blocs-notes q # et Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="21360-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="21360-274">De même, la définition d’opérations requiert uniquement l’écriture du code Q # et l’exécution de la cellule.</span><span class="sxs-lookup"><span data-stu-id="21360-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="21360-275">La sortie répertorie ensuite ces opérations, qui peuvent ensuite être appelées à partir de cellules futures.</span><span class="sxs-lookup"><span data-stu-id="21360-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="21360-276">Ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="21360-276">Target machines</span></span>

<span data-ttu-id="21360-277">Les fonctionnalités permettant d’exécuter des opérations sur des ordinateurs cibles spécifiques sont fournies via les [commandes Magic # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="21360-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="21360-278">Par exemple, utilise `%simulate` le `QuantumSimulator` et `%estimate` utilise les `ResourcesEstimator` éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="21360-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="21360-279">Passage d’entrées aux fonctions et opérations</span><span class="sxs-lookup"><span data-stu-id="21360-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="21360-280">Actuellement, les commandes Magic d’exécution peuvent uniquement être utilisées avec des opérations qui ne prennent pas d’arguments.</span><span class="sxs-lookup"><span data-stu-id="21360-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="21360-281">Ainsi, pour exécuter `MeasureSuperpositionArray` , nous devons définir une opération « wrapper » qui appelle ensuite l’opération avec les arguments :</span><span class="sxs-lookup"><span data-stu-id="21360-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="21360-282">Cette opération peut bien entendu être utilisée de la même façon avec `%estimate` et d’autres commandes d’exécution.</span><span class="sxs-lookup"><span data-stu-id="21360-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
