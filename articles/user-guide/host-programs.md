---
title: 'Méthodes d’exécution d’un :::no-loc(Q#)::: programme'
description: 'Vue d’ensemble des différentes façons d’exécuter des :::no-loc(Q#)::: programmes. À partir de l’invite de commandes, de :::no-loc(Q#)::: blocs-notes Jupyter et de programmes hôtes classiques en Python ou en langage .net.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691704"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="bfe10-104">Méthodes d’exécution d’un :::no-loc(Q#)::: programme</span><span class="sxs-lookup"><span data-stu-id="bfe10-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="bfe10-105">L’un des principaux atouts du kit de développement Quantum est sa flexibilité sur les plateformes et les environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="bfe10-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="bfe10-106">Toutefois, cela signifie également que :::no-loc(Q#)::: les nouveaux utilisateurs peuvent être déconcertés ou submergés par les nombreuses options figurant dans le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="bfe10-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="bfe10-107">Sur cette page, nous expliquons ce qui se passe lors de :::no-loc(Q#)::: l’exécution d’un programme et comparons les différentes façons dont les utilisateurs peuvent le faire.</span><span class="sxs-lookup"><span data-stu-id="bfe10-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="bfe10-108">Une distinction principale est que :::no-loc(Q#)::: peut être exécuté :</span><span class="sxs-lookup"><span data-stu-id="bfe10-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="bfe10-109">en tant qu’application autonome, où :::no-loc(Q#)::: est le seul langage impliqué et le programme est appelé directement.</span><span class="sxs-lookup"><span data-stu-id="bfe10-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="bfe10-110">Deux méthodes appartiennent en fait à cette catégorie :</span><span class="sxs-lookup"><span data-stu-id="bfe10-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="bfe10-111">l’interface de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="bfe10-111">the command-line interface</span></span>
  - <span data-ttu-id="bfe10-112">:::no-loc(Q#)::: Blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="bfe10-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="bfe10-113">avec un *programme hôte* supplémentaire, écrit en Python ou un langage .net (par exemple, C# ou F #), qui appelle ensuite le programme et peut poursuivre le traitement des résultats retournés.</span><span class="sxs-lookup"><span data-stu-id="bfe10-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="bfe10-114">Pour mieux comprendre ces processus et leurs différences, nous envisageons un :::no-loc(Q#)::: programme simple et nous comparons les façons dont il peut être exécuté.</span><span class="sxs-lookup"><span data-stu-id="bfe10-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="bfe10-115">Programme de base :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="bfe10-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="bfe10-116">Un programme Quantum de base peut consister à préparer un qubit dans une superposition égale des États $ \ket {0} $ et $ \ket {1} $, à le mesurer et à retourner le résultat, qui sera, de manière aléatoire, l’un de ces deux États avec une probabilité égale.</span><span class="sxs-lookup"><span data-stu-id="bfe10-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="bfe10-117">En effet, ce processus est au cœur du démarrage rapide du [Générateur de nombres aléatoires quantiques](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="bfe10-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="bfe10-118">Dans :::no-loc(Q#)::: , cette opération est effectuée par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="bfe10-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="bfe10-119">Toutefois, ce code seul ne peut pas être exécuté par :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="bfe10-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="bfe10-120">Pour cela, il doit créer le corps d’une [opération](xref:microsoft.quantum.guide.basics#q-operations-and-functions), qui est ensuite exécutée quand elle est appelée---soit directement, soit par une autre opération.</span><span class="sxs-lookup"><span data-stu-id="bfe10-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="bfe10-121">Par conséquent, vous pouvez écrire une opération de la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="bfe10-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="bfe10-122">Vous avez défini une opération, `MeasureSuperposition` , qui ne prend aucune entrée et retourne une valeur de type [résultat](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="bfe10-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="bfe10-123">Alors que les exemples de cette page consistent uniquement en :::no-loc(Q#)::: *opérations* , tous les concepts que nous aborderons se rapportent de la même façon aux :::no-loc(Q#)::: *fonctions* et, par conséquent, nous les appelons collectivement *callables* .</span><span class="sxs-lookup"><span data-stu-id="bfe10-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="bfe10-124">Leurs différences sont présentées dans [ :::no-loc(Q#)::: concepts de base : les opérations et les fonctions](xref:microsoft.quantum.guide.basics#q-operations-and-functions)et plus d’informations sur leur définition sont disponibles dans [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="bfe10-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="bfe10-125">Pouvant être appelé dans un :::no-loc(Q#)::: fichier</span><span class="sxs-lookup"><span data-stu-id="bfe10-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="bfe10-126">L’appelable est précisément ce qui est appelé et exécuté par :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="bfe10-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="bfe10-127">Toutefois, il faut quelques ajouts pour inclure un `*.qs` :::no-loc(Q#)::: fichier complet.</span><span class="sxs-lookup"><span data-stu-id="bfe10-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="bfe10-128">Tous les :::no-loc(Q#)::: types et callables (ceux que vous définissez et ceux qui sont intrinsèques au langage) sont définis dans les *espaces de noms* , qui fournissent chacun un nom complet qui peut ensuite être référencé.</span><span class="sxs-lookup"><span data-stu-id="bfe10-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="bfe10-129">Par exemple, les [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) opérations et se trouvent dans les [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) espaces de noms et (qui font partie des [ :::no-loc(Q#)::: bibliothèques standard](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="bfe10-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="bfe10-130">En tant que tels, ils peuvent toujours être appelés par le biais de leurs noms *complets* `Microsoft.Quantum.Intrinsic.H(<qubit>)` et `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , mais le fait de toujours effectuer cela entraînerait un code très encombré.</span><span class="sxs-lookup"><span data-stu-id="bfe10-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="bfe10-131">Au lieu de cela, `open` les instructions permettent de référencer callables avec un raccourci plus concis, comme nous l’avons fait dans le corps de l’opération ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="bfe10-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="bfe10-132">Le :::no-loc(Q#)::: fichier complet contenant notre opération consiste donc à définir notre propre espace de noms, à ouvrir les espaces de noms pour les callables que notre opération utilise, puis à exécuter l’opération suivante :</span><span class="sxs-lookup"><span data-stu-id="bfe10-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="bfe10-133">Les espaces de noms peuvent également être dotés d’un *alias* lorsqu’ils sont ouverts, ce qui peut être utile si les noms d’appel/type dans deux espaces de noms sont en conflit.</span><span class="sxs-lookup"><span data-stu-id="bfe10-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="bfe10-134">Par exemple, nous pourrions utiliser à la place `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ci-dessus, puis appeler `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-135">La seule exception est l' [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) espace de noms, qui est toujours ouvert automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bfe10-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="bfe10-136">Par conséquent, callables [`Length`](xref:Microsoft.Quantum.Core.Length) peut toujours être utilisé directement.</span><span class="sxs-lookup"><span data-stu-id="bfe10-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="bfe10-137">En cours d’exécution sur les ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="bfe10-137">Running on target machines</span></span>

<span data-ttu-id="bfe10-138">Désormais, le modèle d’exécution générale d’un :::no-loc(Q#)::: programme devient clair.</span><span class="sxs-lookup"><span data-stu-id="bfe10-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="bfe10-139">Tout d’abord, l’appel spécifique à exécuter a accès à tout autre callables et à tous les types définis dans le même espace de noms.</span><span class="sxs-lookup"><span data-stu-id="bfe10-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="bfe10-140">Elle y accède également à partir de l’une des [ :::no-loc(Q#)::: bibliothèques](xref:microsoft.quantum.libraries), mais celles-ci doivent être référencées par le biais de leur nom complet ou de l’utilisation d' `open` instructions décrites ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="bfe10-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="bfe10-141">L’appel à lui-même est exécuté sur un *[ordinateur cible](xref:microsoft.quantum.machines)* .</span><span class="sxs-lookup"><span data-stu-id="bfe10-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="bfe10-142">Ces machines cibles peuvent être du matériel Quantum réel ou des simulateurs multiples disponibles dans le cadre du QDK.</span><span class="sxs-lookup"><span data-stu-id="bfe10-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="bfe10-143">Dans notre cas, la machine cible la plus utile est une instance du [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , qui calcule le comportement du programme comme s’il était exécuté sur un ordinateur quantique sans bruit.</span><span class="sxs-lookup"><span data-stu-id="bfe10-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="bfe10-144">Jusqu’à présent, nous avons décrit ce qui se produit lorsqu’un :::no-loc(Q#)::: appel spécifique est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="bfe10-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="bfe10-145">Qu’il soit :::no-loc(Q#)::: utilisé dans une application autonome ou avec un programme hôte, ce processus général est plus ou moins le même---donc la flexibilité de QDK.</span><span class="sxs-lookup"><span data-stu-id="bfe10-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="bfe10-146">Les différences entre les méthodes d’appel dans le kit de développement Quantum s’affichent ainsi dans la *manière dont* cet :::no-loc(Q#)::: appel est appelé pour être exécuté, et de quelle manière les résultats sont retournés.</span><span class="sxs-lookup"><span data-stu-id="bfe10-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="bfe10-147">Plus précisément, les différences tournent autour des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bfe10-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="bfe10-148">Indication de l' :::no-loc(Q#)::: appelable à exécuter</span><span class="sxs-lookup"><span data-stu-id="bfe10-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="bfe10-149">Comment les arguments pouvant être appelés peuvent être fournis</span><span class="sxs-lookup"><span data-stu-id="bfe10-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="bfe10-150">Spécification de l’ordinateur cible sur lequel l’exécuter</span><span class="sxs-lookup"><span data-stu-id="bfe10-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="bfe10-151">Comment les résultats sont retournés</span><span class="sxs-lookup"><span data-stu-id="bfe10-151">How any results are returned</span></span>

<span data-ttu-id="bfe10-152">Tout d’abord, nous expliquons comment cela s’effectue avec l' :::no-loc(Q#)::: application autonome à partir de l’invite de commandes, puis passez à l’utilisation des programmes hôtes Python et C#.</span><span class="sxs-lookup"><span data-stu-id="bfe10-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="bfe10-153">Nous nous réservons l’application autonome des :::no-loc(Q#)::: blocs-notes Jupyter pour la dernière version, car contrairement aux trois premières, les fonctionnalités principales ne sont pas centrées autour d’un :::no-loc(Q#)::: fichier local.</span><span class="sxs-lookup"><span data-stu-id="bfe10-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-154">Bien que nous ne les illustrions pas dans ces exemples, l’une des similitudes entre les méthodes d’exécution est que tous les messages imprimés à partir du :::no-loc(Q#)::: programme (à l’aide de [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) ou [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) , par exemple) sont généralement imprimés sur la console respective.</span><span class="sxs-lookup"><span data-stu-id="bfe10-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="bfe10-155">:::no-loc(Q#)::: à partir de l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="bfe10-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="bfe10-156">L’une des méthodes les plus simples pour commencer à écrire :::no-loc(Q#)::: des programmes consiste à éviter d’avoir à vous soucier des fichiers distincts et d’un autre langage.</span><span class="sxs-lookup"><span data-stu-id="bfe10-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="bfe10-157">L’utilisation de Visual Studio Code ou de Visual Studio avec l’extension QDK permet un workflow de travail transparent dans lequel nous exécutons :::no-loc(Q#)::: callables à partir d’un seul :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="bfe10-158">Pour ce faire, nous allons exécuter le programme en entrant</span><span class="sxs-lookup"><span data-stu-id="bfe10-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="bfe10-159">à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="bfe10-159">at the command prompt.</span></span>
<span data-ttu-id="bfe10-160">Le flux de travail le plus simple est lorsque l’emplacement du répertoire du terminal est le même que celui du :::no-loc(Q#)::: fichier, qui peut être facilement géré avec :::no-loc(Q#)::: la modification de fichier à l’aide du terminal intégré dans vs code, par exemple.</span><span class="sxs-lookup"><span data-stu-id="bfe10-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="bfe10-161">Toutefois, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte de nombreuses options et le programme peut également être exécuté à partir d’un emplacement différent en fournissant simplement `--project <PATH>` l’emplacement du :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="bfe10-162">Ajouter un point d’entrée au :::no-loc(Q#)::: fichier</span><span class="sxs-lookup"><span data-stu-id="bfe10-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="bfe10-163">La plupart des :::no-loc(Q#)::: fichiers contiennent plus d’un appelable. naturellement, nous devons laisser le compilateur savoir *quel* appel peut s’exécuter lorsque nous fournissons la `dotnet run` commande.</span><span class="sxs-lookup"><span data-stu-id="bfe10-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="bfe10-164">Cela s’effectue avec une simple modification du :::no-loc(Q#)::: fichier lui-même :</span><span class="sxs-lookup"><span data-stu-id="bfe10-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="bfe10-165">Ajoutez une ligne qui `@EntryPoint()` précède directement l’appelable.</span><span class="sxs-lookup"><span data-stu-id="bfe10-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="bfe10-166">Notre fichier ci-dessus serait donc</span><span class="sxs-lookup"><span data-stu-id="bfe10-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="bfe10-167">À présent, un appel de `dotnet run` à partir de l’invite de commandes provoque `MeasureSuperposition` son exécution, et la valeur retournée est ensuite imprimée directement sur le terminal.</span><span class="sxs-lookup"><span data-stu-id="bfe10-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="bfe10-168">Par conséquent, vous verrez ou vous pouvez l' `One` `Zero` Imprimer.</span><span class="sxs-lookup"><span data-stu-id="bfe10-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="bfe10-169">Notez que cela n’a pas d’importance si vous avez plus de callables défini au-dessous, mais uniquement s' `MeasureSuperposition` exécutera.</span><span class="sxs-lookup"><span data-stu-id="bfe10-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="bfe10-170">En outre, ce n’est pas un problème si votre appelable comprend des [Commentaires de documentation](xref:microsoft.quantum.guide.filestructure#documentation-comments) avant sa déclaration, l' `@EntryPoint()` attribut peut être placé juste au-dessus de lui.</span><span class="sxs-lookup"><span data-stu-id="bfe10-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="bfe10-171">Arguments pouvant être appelés</span><span class="sxs-lookup"><span data-stu-id="bfe10-171">Callable arguments</span></span>

<span data-ttu-id="bfe10-172">Jusqu’à présent, nous avons uniquement considéré une opération qui n’accepte aucune entrée.</span><span class="sxs-lookup"><span data-stu-id="bfe10-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="bfe10-173">Supposons que nous voulions effectuer une opération similaire, mais sur plusieurs qubits---le nombre de qui est fourni en tant qu’argument.</span><span class="sxs-lookup"><span data-stu-id="bfe10-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="bfe10-174">Une telle opération peut être écrite sous la forme</span><span class="sxs-lookup"><span data-stu-id="bfe10-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="bfe10-175">où la valeur retournée est un tableau des résultats de mesure.</span><span class="sxs-lookup"><span data-stu-id="bfe10-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="bfe10-176">Notez que [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) et [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) se trouvent dans [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) les [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) espaces de noms et, nécessitant des `open` instructions supplémentaires pour chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="bfe10-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="bfe10-177">Si vous déplacez l' `@EntryPoint()` attribut pour qu’il précède cette nouvelle opération (Notez qu’il ne peut y avoir qu’une seule ligne dans un fichier), tenter de l’exécuter avec `dotnet run` génère simplement un message d’erreur qui indique les options de ligne de commande supplémentaires requises et comment les exprimer.</span><span class="sxs-lookup"><span data-stu-id="bfe10-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="bfe10-178">Le format général de la ligne de commande est `dotnet run [options]` en réalité, et les arguments pouvant être appelés sont fournis ici.</span><span class="sxs-lookup"><span data-stu-id="bfe10-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="bfe10-179">Dans ce cas, l’argument `n` est manquant et il indique que nous devons fournir l’option `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="bfe10-180">Pour exécuter `MeasureSuperpositionArray` `n=4` qubits, nous utilisons donc</span><span class="sxs-lookup"><span data-stu-id="bfe10-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="bfe10-181">produire une sortie similaire à</span><span class="sxs-lookup"><span data-stu-id="bfe10-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="bfe10-182">Ce bien évidemment s’étend à plusieurs arguments.</span><span class="sxs-lookup"><span data-stu-id="bfe10-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-183">Les noms d’arguments définis dans `camelCase` sont légèrement modifiés par le compilateur pour être acceptés en tant qu' :::no-loc(Q#)::: entrées.</span><span class="sxs-lookup"><span data-stu-id="bfe10-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="bfe10-184">Par exemple, si au lieu de `n` , nous avons utilisé le nom `numQubits` ci-dessus, cette entrée est fournie dans la ligne de commande via à la `--num-qubits 4` place de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="bfe10-185">Le message d’erreur fournit également d’autres options qui peuvent être utilisées, notamment la modification de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="bfe10-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="bfe10-186">Ordinateurs cibles différents</span><span class="sxs-lookup"><span data-stu-id="bfe10-186">Different target machines</span></span>

<span data-ttu-id="bfe10-187">Comme les sorties de nos opérations jusqu’à présent ont été les résultats attendus de leur action sur des qubits réels, il est clair que l’ordinateur cible par défaut à partir de la ligne de commande est le simulateur Quantum à état complet, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="bfe10-188">Toutefois, nous pouvons demander à callables de s’exécuter sur un ordinateur cible spécifique avec l’option `--simulator` (ou le raccourci `-s` ).</span><span class="sxs-lookup"><span data-stu-id="bfe10-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="bfe10-189">Par exemple, nous pourrions l’exécuter sur [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="bfe10-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="bfe10-190">La sortie imprimée est alors</span><span class="sxs-lookup"><span data-stu-id="bfe10-190">The printed output is then</span></span>

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

<span data-ttu-id="bfe10-191">Pour plus d’informations sur ce que ces métriques indiquent, consultez [estimation des ressources : mesures signalées](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="bfe10-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="bfe10-192">Résumé de l’exécution de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="bfe10-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="bfe10-193">Non- :::no-loc(Q#)::: `dotnet run` options</span><span class="sxs-lookup"><span data-stu-id="bfe10-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="bfe10-194">Comme nous l’avons brièvement mentionné plus haut avec l' `--project` option, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte également des options non liées aux :::no-loc(Q#)::: arguments pouvant être appelés.</span><span class="sxs-lookup"><span data-stu-id="bfe10-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="bfe10-195">Si vous fournissez les deux types d’options, les `dotnet` options spécifiques à doivent être fournies en premier, suivies d’un délimiteur, puis des `--` :::no-loc(Q#)::: options spécifiques à.</span><span class="sxs-lookup"><span data-stu-id="bfe10-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="bfe10-196">Par exemple, la spécification d’un chemin d’accès avec un nombre qubits pour l’opération ci-dessus est exécutée via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="bfe10-197">:::no-loc(Q#)::: avec les programmes hôtes</span><span class="sxs-lookup"><span data-stu-id="bfe10-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="bfe10-198">Avec notre :::no-loc(Q#)::: fichier en main, une alternative à l’appel d’une opération ou d’une fonction directement à partir de l’invite de commandes consiste à utiliser un *programme hôte* dans un autre langage classique.</span><span class="sxs-lookup"><span data-stu-id="bfe10-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="bfe10-199">Plus précisément, cela peut être fait avec Python ou un langage .NET tel que C# ou F # (par souci de concision, nous allons uniquement détailler C#).</span><span class="sxs-lookup"><span data-stu-id="bfe10-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="bfe10-200">Un peu plus de configuration est nécessaire pour activer l’interopérabilité, mais ces informations sont disponibles dans les [guides d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="bfe10-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="bfe10-201">En résumé, la situation comprend maintenant un fichier programme hôte (par exemple, `*.py` ou `*.cs` ) au même emplacement que notre :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="bfe10-202">C’est maintenant le programme *hôte* qui est exécuté et, pendant son exécution, il peut appeler des :::no-loc(Q#)::: opérations et des fonctions spécifiques à partir du :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="bfe10-203">Le noyau de l’interopérabilité est basé sur le :::no-loc(Q#)::: compilateur qui rend le contenu du :::no-loc(Q#)::: fichier accessible au programme hôte afin qu’il puisse être appelé.</span><span class="sxs-lookup"><span data-stu-id="bfe10-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="bfe10-204">L’un des principaux avantages de l’utilisation d’un programme hôte est que les données classiques renvoyées par le :::no-loc(Q#)::: programme peuvent ensuite être traitées plus en détail dans la langue de l’hôte.</span><span class="sxs-lookup"><span data-stu-id="bfe10-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="bfe10-205">Cela peut se composer d’un traitement de données avancé (par exemple, une action qui ne peut pas être effectuée en interne dans :::no-loc(Q#)::: ), puis de l’appel d' :::no-loc(Q#)::: actions supplémentaires en fonction de ces résultats, ou d’une opération aussi simple que le traçage des :::no-loc(Q#)::: résultats.</span><span class="sxs-lookup"><span data-stu-id="bfe10-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="bfe10-206">Le schéma général est présenté ici et nous aborderons les implémentations spécifiques de Python et C# ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="bfe10-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="bfe10-207">Vous trouverez un exemple d’utilisation d’un programme hôte F # dans les [exemples d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="bfe10-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="bfe10-208">L' `@EntryPoint()` attribut utilisé pour les :::no-loc(Q#)::: applications ne peut pas être utilisé avec les programmes hôtes.</span><span class="sxs-lookup"><span data-stu-id="bfe10-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="bfe10-209">Une erreur sera déclenchée si elle est présente dans le :::no-loc(Q#)::: fichier appelé par un hôte.</span><span class="sxs-lookup"><span data-stu-id="bfe10-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="bfe10-210">Pour fonctionner avec différents programmes hôtes, aucune modification n’est requise dans un `*.qs` :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="bfe10-211">Les implémentations de programmes hôtes suivantes fonctionnent toutes avec le même :::no-loc(Q#)::: fichier :</span><span class="sxs-lookup"><span data-stu-id="bfe10-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

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

<span data-ttu-id="bfe10-212">Sélectionnez l’onglet correspondant à la langue de votre hôte qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="bfe10-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="bfe10-213">Python</span><span class="sxs-lookup"><span data-stu-id="bfe10-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="bfe10-214">Un programme hôte Python est construit comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfe10-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="bfe10-215">Importez le `qsharp` module, qui inscrit le chargeur de module pour l' :::no-loc(Q#)::: interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="bfe10-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="bfe10-216">Cela permet :::no-loc(Q#)::: d’afficher les espaces de noms en tant que modules python, à partir desquels nous pouvons importer des :::no-loc(Q#)::: callables.</span><span class="sxs-lookup"><span data-stu-id="bfe10-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="bfe10-217">Notez qu’il ne s’agit techniquement pas des :::no-loc(Q#)::: callables qui sont importés, mais plutôt des stubs Python qui permettent de les appeler.</span><span class="sxs-lookup"><span data-stu-id="bfe10-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="bfe10-218">Ils se comportent comme des objets de classes Python.</span><span class="sxs-lookup"><span data-stu-id="bfe10-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="bfe10-219">Nous utilisons des méthodes sur ces objets pour spécifier les ordinateurs cibles auxquels nous envoyons l’opération lors de l’exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="bfe10-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="bfe10-220">Importez ces :::no-loc(Q#)::: callables que nous appellera directement---dans ce cas, `MeasureSuperposition` et `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="bfe10-221">Une fois le `qsharp` module importé, vous pouvez également importer des callables directement à partir des espaces de noms de la :::no-loc(Q#)::: bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="bfe10-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="bfe10-222">Parmi tout autre code Python, vous pouvez maintenant appeler ces callables sur des ordinateurs cibles spécifiques et leur attribuer des retours à des variables (s’ils retournent une valeur) pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="bfe10-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="bfe10-223">Spécification d’ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="bfe10-223">Specifying target machines</span></span>
<span data-ttu-id="bfe10-224">L’appel d’une opération à exécuter sur un ordinateur cible spécifique s’effectue à l’aide de différentes méthodes Python sur l’objet importé.</span><span class="sxs-lookup"><span data-stu-id="bfe10-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="bfe10-225">Par exemple, `.simulate(<args>)` utilise `QuantumSimulator` pour exécuter l’opération, tandis que le `.estimate_resources(<args>)` fait sur le `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="bfe10-226">Passage d’entrées à Q\#</span><span class="sxs-lookup"><span data-stu-id="bfe10-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="bfe10-227">Les arguments de l' :::no-loc(Q#)::: appelable doivent être fournis sous la forme d’un argument de mot clé, où le mot clé est le nom de l’argument dans la :::no-loc(Q#)::: définition pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="bfe10-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="bfe10-228">Autrement dit, `MeasureSuperpositionArray.simulate(n=4)` est valide, alors qu' `MeasureSuperpositionArray.simulate(4)` une erreur est levée.</span><span class="sxs-lookup"><span data-stu-id="bfe10-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="bfe10-229">Par conséquent, le programme hôte python</span><span class="sxs-lookup"><span data-stu-id="bfe10-229">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="bfe10-230">génère une sortie semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="bfe10-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="bfe10-231">Utilisation :::no-loc(Q#)::: de code à partir d’autres projets ou packages</span><span class="sxs-lookup"><span data-stu-id="bfe10-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="bfe10-232">Par défaut, la `import qsharp` commande charge tous les `.qs` fichiers dans le dossier actif et rend leurs :::no-loc(Q#)::: opérations et fonctions disponibles à l’intérieur du script Python.</span><span class="sxs-lookup"><span data-stu-id="bfe10-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="bfe10-233">Pour charger du :::no-loc(Q#)::: code à partir d’un autre dossier, l' [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) peut être utilisée pour ajouter une référence à un `.csproj` fichier pour un :::no-loc(Q#)::: projet (autrement dit, un projet qui référence `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="bfe10-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="bfe10-234">Cette commande permet de compiler tous les `.qs` fichiers du dossier contenant le `.csproj` et ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="bfe10-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="bfe10-235">Il charge également de manière récursive tous les packages référencés via `PackageReference` ou les :::no-loc(Q#)::: projets référencés via `ProjectReference` dans ce `.csproj` fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="bfe10-236">Par exemple, le code python suivant importe un projet externe, en référençant son chemin d’accès relatif au dossier actif, et appelle l’une de ses :::no-loc(Q#)::: opérations :</span><span class="sxs-lookup"><span data-stu-id="bfe10-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="bfe10-237">Cela génère une sortie similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bfe10-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="bfe10-238">Pour charger des packages externes contenant :::no-loc(Q#)::: du code, utilisez l' [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="bfe10-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="bfe10-239">Si le :::no-loc(Q#)::: Code du dossier actif dépend de projets ou de packages externes, vous risquez de rencontrer des erreurs lors de l’exécution de `import qsharp` , puisque les dépendances n’ont pas encore été chargées.</span><span class="sxs-lookup"><span data-stu-id="bfe10-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="bfe10-240">Pour charger des packages ou :::no-loc(Q#)::: des projets externes requis au cours de la `import qsharp` commande, assurez-vous que le dossier contenant le script Python contient un `.csproj` fichier qui fait référence à `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="bfe10-241">Dans cela `.csproj` , ajoutez la propriété `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` à `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="bfe10-242">Cela indique à I :::no-loc(Q#)::: de charger de manière récursive tous `ProjectReference` les `PackageReference` éléments ou trouvés dans celui-ci `.csproj` au cours de la `import qsharp` commande.</span><span class="sxs-lookup"><span data-stu-id="bfe10-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="bfe10-243">Par exemple, voici un fichier simple `.csproj` qui entraîne :::no-loc(Q#)::: le chargement automatique du `Microsoft.Quantum.Chemistry` Package :</span><span class="sxs-lookup"><span data-stu-id="bfe10-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="bfe10-244">Actuellement, cette `<IQSharpLoadAutomatically>` propriété personnalisée est requise par les hôtes Python, mais à l’avenir, cela peut devenir le comportement par défaut d’un `.csproj` fichier situé dans le même dossier que le script Python.</span><span class="sxs-lookup"><span data-stu-id="bfe10-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-245">Actuellement `<QsharpCompile>` , le paramètre dans la `.csproj` est ignoré par les hôtes Python, et tous les `.qs` fichiers dans le dossier du `.csproj` (y compris les sous-dossiers) sont chargés et compilés.</span><span class="sxs-lookup"><span data-stu-id="bfe10-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="bfe10-246">La prise en charge des `.csproj` paramètres sera améliorée dans le futur (pour plus d’informations, consultez [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="bfe10-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="bfe10-247">C#</span><span class="sxs-lookup"><span data-stu-id="bfe10-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="bfe10-248">Un programme hôte C# possède plusieurs composants et fonctionne très étroitement avec certains composants du QDK, tels que les simulateurs, qui sont eux-mêmes basés sur C#.</span><span class="sxs-lookup"><span data-stu-id="bfe10-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="bfe10-249">Le :::no-loc(Q#)::: compilateur fonctionne ici en générant un espace de noms C# nommé de façon équivalente à partir de l' :::no-loc(Q#)::: espace de noms dans notre :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="bfe10-250">Il génère davantage une classe C# nommée de manière équivalente pour chacun des :::no-loc(Q#)::: callables ou types définis dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="bfe10-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="bfe10-251">Tout d’abord, nous faisons en sorte que toutes les classes utilisées dans notre programme hôte soient disponibles avec des `using` instructions, qui sont à peu près analogue aux `open` instructions de notre :::no-loc(Q#)::: fichier :</span><span class="sxs-lookup"><span data-stu-id="bfe10-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="bfe10-252">Ensuite, nous déclarons notre espace de noms C#, quelques autres bits et éléments (consultez le bloc de code complet ci-dessous), puis toute programmation classique que nous aimerions (par exemple, le calcul d’arguments pour le :::no-loc(Q#)::: callables).</span><span class="sxs-lookup"><span data-stu-id="bfe10-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="bfe10-253">Ce dernier n’est pas nécessaire dans notre cas, mais un exemple d’utilisation de ce type est disponible dans l'  [exemple d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="bfe10-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="bfe10-254">Ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="bfe10-254">Target machines</span></span>

<span data-ttu-id="bfe10-255">En revenons à :::no-loc(Q#)::: , nous devons créer une instance de n’importe quelle machine cible sur laquelle nous allons exécuter nos opérations.</span><span class="sxs-lookup"><span data-stu-id="bfe10-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="bfe10-256">L’utilisation d’autres ordinateurs cibles est aussi simple que l’instanciation d’un autre ordinateur, bien que la manière de procéder et le traitement des retours puissent être légèrement différents.</span><span class="sxs-lookup"><span data-stu-id="bfe10-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="bfe10-257">Par souci de concision, nous nous contenterons pour l' [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) instant, et inclurons les [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [ci-dessous](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="bfe10-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="bfe10-258">Chaque classe C# générée à partir des :::no-loc(Q#)::: opérations a une `Run` méthode, dont le premier argument doit être l’instance de machine cible.</span><span class="sxs-lookup"><span data-stu-id="bfe10-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="bfe10-259">Ainsi, pour exécuter `MeasureSuperposition` sur le `QuantumSimulator` , nous utilisons `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="bfe10-260">Les résultats retournés peuvent ensuite être affectés à des variables en C# :</span><span class="sxs-lookup"><span data-stu-id="bfe10-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="bfe10-261">La `Run` méthode est exécutée de façon asynchrone, car ce sera le cas pour le matériel Quantum réel. par conséquent, le `await` mot clé bloque tout traitement supplémentaire jusqu’à ce que la tâche se termine.</span><span class="sxs-lookup"><span data-stu-id="bfe10-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="bfe10-262">Si l' :::no-loc(Q#)::: appelable n’a pas de retour (par exemple, s’il a un type de retour `Unit` ), l’exécution peut toujours être effectuée de la même manière sans l’assigner à une variable.</span><span class="sxs-lookup"><span data-stu-id="bfe10-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="bfe10-263">Dans ce cas, la ligne entière se compose simplement de</span><span class="sxs-lookup"><span data-stu-id="bfe10-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="bfe10-264">Arguments</span><span class="sxs-lookup"><span data-stu-id="bfe10-264">Arguments</span></span>

<span data-ttu-id="bfe10-265">Tous les arguments de l' :::no-loc(Q#)::: appelable sont simplement passés en tant qu’arguments supplémentaires après l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="bfe10-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="bfe10-266">Par conséquent, les résultats de `MeasureSuperpositionArray` sur `n=4` qubits seraient récupérés via</span><span class="sxs-lookup"><span data-stu-id="bfe10-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="bfe10-267">Un programme hôte C# complet peut donc ressembler à</span><span class="sxs-lookup"><span data-stu-id="bfe10-267">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="bfe10-268">À l’emplacement du fichier C#, le programme hôte peut être exécuté à partir de l’invite de commandes en entrant</span><span class="sxs-lookup"><span data-stu-id="bfe10-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="bfe10-269">dans ce cas, vous verrez une sortie écrite dans la console, similaire à</span><span class="sxs-lookup"><span data-stu-id="bfe10-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="bfe10-270">En raison de l’interopérabilité du compilateur avec les espaces de noms, nous pourrions également rendre notre :::no-loc(Q#)::: callables disponible sans l' `using NamespaceName;` instruction et en faisant simplement correspondre le titre de l’espace de noms C# à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="bfe10-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="bfe10-271">Autrement dit, en remplaçant `namespace host` par `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="bfe10-272">Inclusion de l’estimateur de ressources</span><span class="sxs-lookup"><span data-stu-id="bfe10-272">Including the resources estimator</span></span>

<span data-ttu-id="bfe10-273">Le [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requiert une implémentation légèrement différente pour récupérer la sortie.</span><span class="sxs-lookup"><span data-stu-id="bfe10-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="bfe10-274">Tout d’abord, au lieu de les instancier en tant que variable avec une `using` instruction (comme nous le faisons avec `QuantumSimulator` ), nous instancions plus directement les objets de la classe via</span><span class="sxs-lookup"><span data-stu-id="bfe10-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="bfe10-275">Notez qu’au lieu d’utiliser un simulateur cible unique pour plusieurs :::no-loc(Q#)::: opérations, nous avons instancié un pour chaque.</span><span class="sxs-lookup"><span data-stu-id="bfe10-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="bfe10-276">Cela est dû au fait que les objets eux-mêmes sont modifiés lorsqu’ils sont utilisés en tant qu’ordinateurs cibles, et que leurs résultats peuvent ensuite être récupérés ultérieurement avec la méthode de classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="bfe10-277">Pour exécuter les opérations sur les estimateurs de ressources, nous utilisons</span><span class="sxs-lookup"><span data-stu-id="bfe10-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="bfe10-278">puis, récupérez les résultats sous forme de valeurs séparées par des tabulations (TSV) avec `estimatorSingleQ.ToTSV()` et `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="bfe10-279">Ainsi, un programme hôte C# complet qui utilise à la fois le `QuantumSimulator` et `ResourcesEstimator` peut prendre la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="bfe10-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="bfe10-280">ce qui donne une sortie similaire à</span><span class="sxs-lookup"><span data-stu-id="bfe10-280">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="bfe10-281">:::no-loc(Q#)::: Blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="bfe10-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="bfe10-282">:::no-loc(Q#)::: Les blocs-notes Jupyter utilisent le :::no-loc(Q#)::: noyau I, qui vous permet de définir, compiler et exécuter des :::no-loc(Q#)::: callables dans un seul bloc-notes---à côté des instructions, des notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="bfe10-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="bfe10-283">Cela signifie que, bien qu’il soit possible d’importer et d’utiliser le contenu de `*.qs` :::no-loc(Q#)::: fichiers, ils ne sont pas nécessaires dans le modèle d’exécution.</span><span class="sxs-lookup"><span data-stu-id="bfe10-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="bfe10-284">Ici, nous allons expliquer en détail comment exécuter les :::no-loc(Q#)::: opérations définies ci-dessus, mais une introduction plus étendue à l’utilisation des :::no-loc(Q#)::: blocs-notes Jupyter est fournie à l' [Introduction à :::no-loc(Q#)::: et aux blocs-notes Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="bfe10-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="bfe10-285">Définition des opérations</span><span class="sxs-lookup"><span data-stu-id="bfe10-285">Defining operations</span></span>

<span data-ttu-id="bfe10-286">Dans un :::no-loc(Q#)::: Jupyter Notebook, vous entrez du :::no-loc(Q#)::: code comme nous le feriez à l’intérieur de l’espace de noms d’un :::no-loc(Q#)::: fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="bfe10-287">Nous pouvons donc activer l’accès à callables à partir des [ :::no-loc(Q#)::: bibliothèques standard](xref:microsoft.quantum.qsharplibintro) avec des `open` instructions pour leurs espaces de noms respectifs.</span><span class="sxs-lookup"><span data-stu-id="bfe10-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="bfe10-288">Lors de l’exécution d’une cellule avec une telle instruction, les définitions de ces espaces de noms sont disponibles dans l’ensemble de l’espace de travail.</span><span class="sxs-lookup"><span data-stu-id="bfe10-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-289">Callables de [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic) et [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (par exemple, [`H`](xref:Microsoft.Quantum.Intrinsic.H) et [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) sont automatiquement disponibles pour les opérations définies dans des cellules dans des :::no-loc(Q#)::: blocs-notes Jupyter.</span><span class="sxs-lookup"><span data-stu-id="bfe10-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="bfe10-290">Toutefois, cela n’est pas le cas pour le code provenant de :::no-loc(Q#)::: fichiers sources externes (processus présenté à l' [Introduction à :::no-loc(Q#)::: et les blocs-notes Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="bfe10-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="bfe10-291">De même, la définition d’opérations requiert uniquement l’écriture du :::no-loc(Q#)::: code et l’exécution de la cellule.</span><span class="sxs-lookup"><span data-stu-id="bfe10-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="bfe10-292">La sortie répertorie ensuite ces opérations, qui peuvent ensuite être appelées à partir de cellules futures.</span><span class="sxs-lookup"><span data-stu-id="bfe10-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="bfe10-293">Ordinateurs cibles</span><span class="sxs-lookup"><span data-stu-id="bfe10-293">Target machines</span></span>

<span data-ttu-id="bfe10-294">Les fonctionnalités permettant d’exécuter des opérations sur des ordinateurs cibles spécifiques sont fournies via les [ :::no-loc(Q#)::: commandes magiques](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="bfe10-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="bfe10-295">Par exemple, utilise `%simulate` le `QuantumSimulator` et `%estimate` utilise les `ResourcesEstimator` éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bfe10-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="bfe10-296">Passage d’entrées aux fonctions et opérations</span><span class="sxs-lookup"><span data-stu-id="bfe10-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="bfe10-297">Pour passer des entrées aux :::no-loc(Q#)::: opérations, les arguments peuvent être passés en tant que `key=value` paires à la commande Run Magic.</span><span class="sxs-lookup"><span data-stu-id="bfe10-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="bfe10-298">Ainsi, pour exécuter `MeasureSuperpositionArray` avec quatre qubits, nous pouvons exécuter `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="bfe10-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="bfe10-299">Ce modèle peut être utilisé de la même façon avec `%estimate` et d’autres commandes Run.</span><span class="sxs-lookup"><span data-stu-id="bfe10-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="bfe10-300">Utilisation :::no-loc(Q#)::: de code à partir d’autres projets ou packages</span><span class="sxs-lookup"><span data-stu-id="bfe10-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="bfe10-301">Par défaut, un :::no-loc(Q#)::: Jupyter Notebook charge tous les `.qs` fichiers du dossier actif et rend leurs :::no-loc(Q#)::: opérations et fonctions disponibles à l’intérieur du bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="bfe10-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="bfe10-302">La [ `%who` commande Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) répertorie toutes les :::no-loc(Q#)::: opérations et fonctions actuellement disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfe10-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="bfe10-303">Pour charger du :::no-loc(Q#)::: code à partir d’un autre dossier, vous pouvez utiliser la [ `%project` commande Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) pour ajouter une référence à un `.csproj` fichier pour un :::no-loc(Q#)::: projet (autrement dit, un projet qui fait référence à `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="bfe10-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="bfe10-304">Cette commande permet de compiler tous les `.qs` fichiers du dossier contenant les `.csproj` sous-dossiers (et).</span><span class="sxs-lookup"><span data-stu-id="bfe10-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="bfe10-305">Il charge également de manière récursive tous les packages référencés via `PackageReference` ou les :::no-loc(Q#)::: projets référencés via `ProjectReference` dans ce `.csproj` fichier.</span><span class="sxs-lookup"><span data-stu-id="bfe10-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="bfe10-306">Par exemple, les cellules suivantes simulent une :::no-loc(Q#)::: opération à partir d’un projet externe, où le chemin d’accès du projet est référencé par rapport au dossier actuel :</span><span class="sxs-lookup"><span data-stu-id="bfe10-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="bfe10-307">Pour charger des packages externes contenant :::no-loc(Q#)::: du code, utilisez la [ `%package` commande Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="bfe10-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="bfe10-308">Le chargement d’un package rend également disponibles toutes les commandes magiques personnalisées ou les encodeurs d’affichage contenus dans les assemblys qui font partie du package.</span><span class="sxs-lookup"><span data-stu-id="bfe10-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="bfe10-309">Pour charger des packages ou des :::no-loc(Q#)::: projets externes au moment de la initialisation du bloc-notes, vérifiez que le dossier du bloc-notes contient un `.csproj` fichier qui fait référence à `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="bfe10-310">Dans cela `.csproj` , ajoutez la propriété `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` à `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="bfe10-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="bfe10-311">Cela permet :::no-loc(Q#)::: de charger de manière récursive tous les `ProjectReference` éléments ou `PackageReference` trouvés dans qui, `.csproj` au moment du chargement du bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="bfe10-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="bfe10-312">Par exemple, voici un fichier simple `.csproj` qui entraîne :::no-loc(Q#)::: le chargement automatique du `Microsoft.Quantum.Chemistry` Package :</span><span class="sxs-lookup"><span data-stu-id="bfe10-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="bfe10-313">Actuellement, cette `<IQSharpLoadAutomatically>` propriété personnalisée est requise par :::no-loc(Q#)::: les hôtes Jupyter Notebook, mais à l’avenir, cela peut devenir le comportement par défaut d’un `.csproj` fichier situé dans le même dossier que le fichier de bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="bfe10-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="bfe10-314">Actuellement `<QsharpCompile>` , le paramètre dans la `.csproj` est ignoré par les :::no-loc(Q#)::: hôtes Jupyter Notebook et tous les `.qs` fichiers du dossier du `.csproj` (y compris les sous-dossiers) sont chargés et compilés.</span><span class="sxs-lookup"><span data-stu-id="bfe10-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="bfe10-315">La prise en charge des `.csproj` paramètres sera améliorée dans le futur (pour plus d’informations, consultez [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="bfe10-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
