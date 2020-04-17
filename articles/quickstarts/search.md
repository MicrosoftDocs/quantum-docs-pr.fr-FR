---
title: Exécuter l’algorithme de recherche de Grover en Q# – Quantum Development Kit
description: Créez un projet Q# illustrant l’algorithme de Grover, l’un des algorithmes quantiques canoniques.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906948"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Démarrage rapide : Implémenter l’algorithme de recherche de Grover en Q#

Dans ce guide de démarrage rapide, vous pouvez apprendre à créer et exécuter une recherche de Grover pour accélérer la recherche de données non structurées.  La recherche de Grover est l’un des algorithmes d’informatique quantique les plus connus. Cette implémentation Q# relativement petite vous donne une idée des avantages que représente la programmation de solutions quantiques en utilisant un langage de programmation Q# général pour exprimer des algorithmes quantiques.  À la fin de ce guide, la simulation vous montrera une recherche aboutie d’une chaîne spécifique parmi une liste d’entrées non organisées en une fraction du temps qu’il aurait fallu à un ordinateur classique pour le faire.

L’algorithme de Grover recherche des éléments spécifiques dans une liste de données non structurées. Par exemple, il peut répondre à la question : Cette carte tirée d’un jeu de cartes est-elle un as de cœur ? Le libellé de l’élément spécifique est nommé _entrée marquée_.

L’algorithme de recherche de Grover permet à un ordinateur quantique d’effectuer cette recherche en moins d’étapes qu’il n’y d’éléments dans la liste, ce qu’aucun algorithme classique ne permet de faire. Le gain de vitesse dans le cas d’un jeu de cartes est négligeable. En revanche, dans des listes contenant des millions voire des milliards d’éléments, il devient significatif.

Il est possible de construire l’algorithme de recherche de Grover en seulement quelques lignes de code.

## <a name="prerequisites"></a>Prérequis

- Le Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Que fait l’algorithme de recherche de Grover ?

L’algorithme de Grover demande si un élément figurant dans une est celui recherché. Pour ce faire, il construit une superposition quantique des index de la liste où chaque coefficient, ou amplitude de probabilité, représente la probabilité qu’un index spécifique soit celui qui est recherche.

L’algorithme comprend deux étapes qui augmentent de façon incrémentielle le coefficient de l’index recherché, jusqu’à ce que l’amplitude de probabilité du coefficient soit proche de un.

Le nombre d’augmentations incrémentielles est inférieur au nombre d’éléments de la liste. C’est pourquoi l’algorithme de recherche de Grover effectue la recherche en moins d’étapes que n’importe quel algorithme classique.

![Diagramme fonctionnel de l’algorithme de recherche de Grover](~/media/grover.png)

## <a name="write-the-code"></a>Écrire le code

1. À l’aide du Quantum Development Kit, [créez un projet Q#](xref:microsoft.quantum.howto.createproject) nommé `Grover` dans l’environnement de développement de votre choix.

1. Ajoutez le code suivant au fichier `Operations.qs` de votre nouveau projet :

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Pour définir la liste que nous recherchons, créez un fichier `Reflections.qs` et collez-y le code suivant :

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    L’opération `ReflectAboutMarked` définit l’entrée marquée que vous recherchez, à savoir la chaîne de zéros et de uns alternés. Cet exemple code en dur l’entrée marquée. Il peut être étendu à la recherche d’autres entrées ou généralisé pour toute entrée.

1. Ensuite, exécutez votre nouveau programme Q# pour rechercher l’élément marqué par `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python avec Visual Studio Code ou la ligne de commande](#tab/tabid-python)

    Pour exécuter votre nouveau programme Q# à partir de Python, enregistrez le code suivant sous le nom `host.py` :

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# avec Visual Studio Code ou la ligne de commande](#tab/tabid-csharp)

    Pour exécuter votre nouveau programme Q# à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# avec Visual Studio 2019](#tab/tabid-vs2019)

    Pour exécuter votre nouveau programme Q# à partir de C# dans Visual Studio, modifiez `Driver.cs` pour inclure le code C# suivant :

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec les résultats suivants : 

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

    L’opération `ReflectAboutMarked` n’a été appelée que quatre fois, mais votre programme Q# a été capable de trouver l’entrée « 01010 » parmi $2^{5} = 32$ entrées possibles !

## <a name="next-steps"></a>Étapes suivantes

Si vous avez apprécié ce démarrage rapide, consultez certaines des ressources ci-dessous pour apprendre à utiliser le langage Q# pour écrire vos propres applications quantiques :

- [Retour au guide de démarrage avec le QDK](xref:microsoft.quantum.welcome)
- Essayer un [exemple](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) d’algorithme de recherche de Grover plus général
- [En savoir plus sur la recherche de Grover avec les katas quantiques](xref:microsoft.quantum.overview.katas)
- En savoir plus sur l’[amplification d’amplitude](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la technique d’informatique quantique derrière l’algorithme de recherche de Grover
- [Concepts de l’informatique quantique](xref:microsoft.quantum.concepts.intro)
- [Exemples du Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
