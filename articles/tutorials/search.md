---
title: Exécuter l’algorithme de recherche de Grover en Q# – Quantum Development Kit
description: Créez un projet Q# illustrant l’algorithme de Grover, l’un des algorithmes quantiques canoniques.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9e4c53b4d5159cf07f0654603c1d477ad09eb7c6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274743"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="13ff7-103">Tutoriel : Implémenter l’algorithme de recherche de Grover en Q\#</span><span class="sxs-lookup"><span data-stu-id="13ff7-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="13ff7-104">Dans ce tutoriel, vous pouvez apprendre à créer et exécuter une recherche de Grover pour accélérer la recherche de données non structurées.</span><span class="sxs-lookup"><span data-stu-id="13ff7-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="13ff7-105">La recherche de Grover est l’un des algorithmes d’informatique quantique les plus connus. Cette implémentation Q# relativement petite vous donne une idée des avantages que représente la programmation de solutions quantiques en utilisant un langage de programmation Q# général pour exprimer des algorithmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="13ff7-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="13ff7-106">À la fin de ce guide, la simulation vous montrera une recherche aboutie d’une chaîne spécifique parmi une liste d’entrées non organisées en une fraction du temps qu’il aurait fallu à un ordinateur classique pour le faire.</span><span class="sxs-lookup"><span data-stu-id="13ff7-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="13ff7-107">L’algorithme de Grover recherche des éléments spécifiques dans une liste de données non structurées.</span><span class="sxs-lookup"><span data-stu-id="13ff7-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="13ff7-108">Par exemple, il peut répondre à la question : Cette carte tirée d’un jeu de cartes est-elle un as de cœur ?</span><span class="sxs-lookup"><span data-stu-id="13ff7-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="13ff7-109">Le libellé de l’élément spécifique est nommé _entrée marquée_.</span><span class="sxs-lookup"><span data-stu-id="13ff7-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="13ff7-110">L’algorithme de recherche de Grover permet à un ordinateur quantique d’effectuer cette recherche en moins d’étapes qu’il n’y d’éléments dans la liste, ce qu’aucun algorithme classique ne permet de faire.</span><span class="sxs-lookup"><span data-stu-id="13ff7-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="13ff7-111">Le gain de vitesse dans le cas d’un jeu de cartes est négligeable. En revanche, dans des listes contenant des millions voire des milliards d’éléments, il devient significatif.</span><span class="sxs-lookup"><span data-stu-id="13ff7-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="13ff7-112">Il est possible de construire l’algorithme de recherche de Grover en seulement quelques lignes de code.</span><span class="sxs-lookup"><span data-stu-id="13ff7-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13ff7-113">Prérequis</span><span class="sxs-lookup"><span data-stu-id="13ff7-113">Prerequisites</span></span>

- <span data-ttu-id="13ff7-114">Le Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="13ff7-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="13ff7-115">Que fait l’algorithme de recherche de Grover ?</span><span class="sxs-lookup"><span data-stu-id="13ff7-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="13ff7-116">L’algorithme de Grover demande si un élément figurant dans une est celui recherché.</span><span class="sxs-lookup"><span data-stu-id="13ff7-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="13ff7-117">Pour ce faire, il construit une superposition quantique des index de la liste où chaque coefficient, ou amplitude de probabilité, représente la probabilité qu’un index spécifique soit celui qui est recherche.</span><span class="sxs-lookup"><span data-stu-id="13ff7-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="13ff7-118">L’algorithme comprend deux étapes qui augmentent de façon incrémentielle le coefficient de l’index recherché, jusqu’à ce que l’amplitude de probabilité du coefficient soit proche de un.</span><span class="sxs-lookup"><span data-stu-id="13ff7-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="13ff7-119">Le nombre d’augmentations incrémentielles est inférieur au nombre d’éléments de la liste.</span><span class="sxs-lookup"><span data-stu-id="13ff7-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="13ff7-120">C’est pourquoi l’algorithme de recherche de Grover effectue la recherche en moins d’étapes que n’importe quel algorithme classique.</span><span class="sxs-lookup"><span data-stu-id="13ff7-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagramme fonctionnel de l’algorithme de recherche de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="13ff7-122">Écrire le code</span><span class="sxs-lookup"><span data-stu-id="13ff7-122">Write the code</span></span>

1. <span data-ttu-id="13ff7-123">À l’aide du kit de développement Quantum, [créez un projet Q# pour l’application en ligne de commande](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="13ff7-123">Using the Quantum Development Kit, [create a new Q# project for the command line application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="13ff7-124">Intitulez le projet `Grover`.</span><span class="sxs-lookup"><span data-stu-id="13ff7-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="13ff7-125">Ajoutez le code suivant au fichier `Program.qs` de votre nouveau projet :</span><span class="sxs-lookup"><span data-stu-id="13ff7-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="13ff7-126">Pour définir la liste que nous recherchons, créez un fichier `Reflections.qs` et collez-y le code suivant :</span><span class="sxs-lookup"><span data-stu-id="13ff7-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="13ff7-127">L’opération `ReflectAboutMarked` définit l’entrée marquée que vous recherchez, à savoir la chaîne de zéros et de uns alternés.</span><span class="sxs-lookup"><span data-stu-id="13ff7-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="13ff7-128">Cet exemple code en dur l’entrée marquée. Il peut être étendu à la recherche d’autres entrées ou généralisé pour toute entrée.</span><span class="sxs-lookup"><span data-stu-id="13ff7-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="13ff7-129">Ensuite, exécutez votre nouveau programme Q# pour rechercher l’élément marqué par `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="13ff7-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="13ff7-130">Applications de ligne de commande Q# avec Visual Studio ou Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="13ff7-130">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="13ff7-131">L’exécutable exécute l’opération ou la fonction marquée avec l’attribut `@EntryPoint()` sur un simulateur ou un estimateur de ressources, en fonction de la configuration du projet et des options de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="13ff7-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="13ff7-132">Dans Visual Studio, appuyez simplement sur CTRL + F5 pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="13ff7-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="13ff7-133">Dans VS Code, générez le `Program.qs` pour la première fois en tapant le texte ci-dessous dans le terminal :</span><span class="sxs-lookup"><span data-stu-id="13ff7-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="13ff7-134">Pour les exécutions suivantes, il n’est pas nécessaire de le regénérer.</span><span class="sxs-lookup"><span data-stu-id="13ff7-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="13ff7-135">Pour l’exécuter, tapez la commande suivante et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="13ff7-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="13ff7-136">Vous devriez voir le message suivant dans le terminal :</span><span class="sxs-lookup"><span data-stu-id="13ff7-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="13ff7-137">C’est parce que vous n’avez pas spécifié le nombre de qubits que vous vouliez utiliser, donc le terminal vous indique les commandes disponibles pour l’exécutable.</span><span class="sxs-lookup"><span data-stu-id="13ff7-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="13ff7-138">Si nous souhaitons utiliser 5 qubits, nous devons taper :</span><span class="sxs-lookup"><span data-stu-id="13ff7-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="13ff7-139">En appuyant sur Entrée, vous devriez normalement voir la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="13ff7-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="13ff7-140">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="13ff7-140">Next steps</span></span>

<span data-ttu-id="13ff7-141">Si ce tutoriel vous a plu, consultez certaines des ressources ci-dessous pour apprendre à utiliser le langage Q# afin d’écrire vos propres applications quantiques :</span><span class="sxs-lookup"><span data-stu-id="13ff7-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="13ff7-142">Retour au guide de démarrage avec le QDK</span><span class="sxs-lookup"><span data-stu-id="13ff7-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="13ff7-143">Essayer un [exemple](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) d’algorithme de recherche de Grover plus général</span><span class="sxs-lookup"><span data-stu-id="13ff7-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="13ff7-144">En savoir plus sur la recherche de Grover avec les katas quantiques</span><span class="sxs-lookup"><span data-stu-id="13ff7-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="13ff7-145">En savoir plus sur l’[amplification d’amplitude][amplitude-amplification], la technique d’informatique quantique derrière l’algorithme de recherche de Grover</span><span class="sxs-lookup"><span data-stu-id="13ff7-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="13ff7-146">Concepts de l’informatique quantique</span><span class="sxs-lookup"><span data-stu-id="13ff7-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="13ff7-147">Exemples du Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="13ff7-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
