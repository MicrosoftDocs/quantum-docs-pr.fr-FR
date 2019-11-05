---
title: Exécuter l’algorithme de recherche de Grover en Q# – Quantum Development Kit
description: Créez un projet Q# illustrant l’algorithme de Grover, l’un des algorithmes quantiques canoniques.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443934"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="dc7e8-103">Démarrage rapide : Implémenter l’algorithme de recherche de Grover en Q#</span><span class="sxs-lookup"><span data-stu-id="dc7e8-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="dc7e8-104">Dans ce guide de démarrage rapide, vous pouvez apprendre à créer et exécuter une recherche de Grover pour accélérer la recherche de données non structurées.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="dc7e8-105">La recherche de Grover est l’un des algorithmes d’informatique quantique les plus connus. Cette implémentation Q# relativement petite vous donne une idée des avantages que représente la programmation de solutions quantiques en utilisant un langage de programmation Q# général pour exprimer des algorithmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="dc7e8-106">À la fin de ce guide, la simulation vous montrera une recherche aboutie d’une chaîne spécifique parmi une liste d’entrées non organisées en une fraction du temps qu’il aurait fallu à un ordinateur classique pour le faire.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="dc7e8-107">L’algorithme de Grover recherche des éléments spécifiques dans une liste de données non structurées.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="dc7e8-108">Par exemple, il peut répondre à la question : Cette carte tirée d’un jeu de cartes est-elle un as de cœur ?</span><span class="sxs-lookup"><span data-stu-id="dc7e8-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="dc7e8-109">Le libellé de l’élément spécifique est nommé _entrée marquée_.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="dc7e8-110">L’algorithme de recherche de Grover permet à un ordinateur quantique d’effectuer cette recherche en moins d’étapes qu’il n’y d’éléments dans la liste, ce qu’aucun algorithme classique ne permet de faire.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="dc7e8-111">Le gain de vitesse dans le cas d’un jeu de cartes est négligeable. En revanche, dans des listes contenant des millions voire des milliards d’éléments, il devient significatif.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="dc7e8-112">Il est possible de construire l’algorithme de recherche de Grover en seulement quelques lignes de code.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc7e8-113">Prérequis</span><span class="sxs-lookup"><span data-stu-id="dc7e8-113">Prerequisites</span></span>

- <span data-ttu-id="dc7e8-114">Le Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="dc7e8-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="dc7e8-115">Que fait l’algorithme de recherche de Grover ?</span><span class="sxs-lookup"><span data-stu-id="dc7e8-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="dc7e8-116">L’algorithme de Grover demande si un élément figurant dans une est celui recherché.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="dc7e8-117">Pour ce faire, il construit une superposition quantique des index de la liste où chaque coefficient, ou amplitude de probabilité, représente la probabilité qu’un index spécifique soit celui qui est recherche.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="dc7e8-118">L’algorithme comprend deux étapes qui augmentent de façon incrémentielle le coefficient de l’index recherché, jusqu’à ce que l’amplitude de probabilité du coefficient soit proche de un.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="dc7e8-119">Le nombre d’augmentations incrémentielles est inférieur au nombre d’éléments de la liste.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="dc7e8-120">C’est pourquoi l’algorithme de recherche de Grover effectue la recherche en moins d’étapes que n’importe quel algorithme classique.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagramme fonctionnel de l’algorithme de recherche de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="dc7e8-122">Écrire le code</span><span class="sxs-lookup"><span data-stu-id="dc7e8-122">Write the code</span></span>

1. <span data-ttu-id="dc7e8-123">À l’aide du Quantum Development Kit, [créez un projet Q#](xref:microsoft.quantum.howto.createproject) nommé `Grover` dans l’environnement de développement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="dc7e8-124">Ajoutez le code suivant au fichier `Operations.qs` de votre nouveau projet :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="dc7e8-125">Pour définir la liste que nous recherchons, créez un fichier `Reflections.qs` et collez-y le code suivant :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="dc7e8-126">L’opération `ReflectAboutMarked` définit l’entrée marquée que vous recherchez, à savoir la chaîne de zéros et de uns alternés.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="dc7e8-127">Cet exemple code en dur l’entrée marquée. Il peut être étendu à la recherche d’autres entrées ou généralisé pour toute entrée.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="dc7e8-128">Ensuite, exécutez votre nouveau programme Q# pour rechercher l’élément marqué par `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="dc7e8-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="dc7e8-129">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="dc7e8-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="dc7e8-130">Pour exécuter votre nouveau programme Q# à partir de Python, enregistrez le code suivant sous le nom `host.py` :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="dc7e8-131">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="dc7e8-132">C# avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="dc7e8-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="dc7e8-133">Pour exécuter votre nouveau programme Q# à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="dc7e8-134">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="dc7e8-135">C# avec Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="dc7e8-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="dc7e8-136">Pour exécuter votre nouveau programme Q# à partir de C# dans Visual Studio, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="dc7e8-137">Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="dc7e8-138">L’opération `ReflectAboutMarked` n’a été appelée que quatre fois, mais votre programme Q# a été capable de trouver l’entrée « 01010 » parmi $2^{5} = 32$ entrées possibles !</span><span class="sxs-lookup"><span data-stu-id="dc7e8-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc7e8-139">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="dc7e8-139">Next steps</span></span>

<span data-ttu-id="dc7e8-140">Si vous avez apprécié ce démarrage rapide, consultez certaines des ressources ci-dessous pour apprendre à utiliser le langage Q# pour écrire vos propres applications quantiques :</span><span class="sxs-lookup"><span data-stu-id="dc7e8-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="dc7e8-141">Retour au guide de démarrage avec le QDK</span><span class="sxs-lookup"><span data-stu-id="dc7e8-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="dc7e8-142">Essayer un [exemple](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) d’algorithme de recherche de Grover plus général</span><span class="sxs-lookup"><span data-stu-id="dc7e8-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="dc7e8-143">En savoir plus sur la recherche de Grover avec les katas quantiques</span><span class="sxs-lookup"><span data-stu-id="dc7e8-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="dc7e8-144">En savoir plus sur l’[amplification d’amplitude](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la technique d’informatique quantique derrière l’algorithme de recherche de Grover</span><span class="sxs-lookup"><span data-stu-id="dc7e8-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="dc7e8-145">Concepts de l’informatique quantique</span><span class="sxs-lookup"><span data-stu-id="dc7e8-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="dc7e8-146">Exemples du Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="dc7e8-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
