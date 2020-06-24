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
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Tutoriel : Implémenter l’algorithme de recherche de Grover en Q\#

Dans ce tutoriel, vous pouvez apprendre à créer et exécuter une recherche de Grover pour accélérer la recherche de données non structurées.  La recherche de Grover est l’un des algorithmes d’informatique quantique les plus connus. Cette implémentation Q# relativement petite vous donne une idée des avantages que représente la programmation de solutions quantiques en utilisant un langage de programmation Q# général pour exprimer des algorithmes quantiques.  À la fin de ce guide, la simulation vous montrera une recherche aboutie d’une chaîne spécifique parmi une liste d’entrées non organisées en une fraction du temps qu’il aurait fallu à un ordinateur classique pour le faire.

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

1. À l’aide du kit de développement Quantum, [créez un projet Q# pour l’application en ligne de commande](xref:microsoft.quantum.install.standalone). Intitulez le projet `Grover`.

1. Ajoutez le code suivant au fichier `Program.qs` de votre nouveau projet :

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Pour définir la liste que nous recherchons, créez un fichier `Reflections.qs` et collez-y le code suivant :

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    L’opération `ReflectAboutMarked` définit l’entrée marquée que vous recherchez, à savoir la chaîne de zéros et de uns alternés. Cet exemple code en dur l’entrée marquée. Il peut être étendu à la recherche d’autres entrées ou généralisé pour toute entrée.

1. Ensuite, exécutez votre nouveau programme Q# pour rechercher l’élément marqué par `ReflectAboutMarked`.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Applications de ligne de commande Q# avec Visual Studio ou Visual Studio Code

L’exécutable exécute l’opération ou la fonction marquée avec l’attribut `@EntryPoint()` sur un simulateur ou un estimateur de ressources, en fonction de la configuration du projet et des options de ligne de commande.

Dans Visual Studio, appuyez simplement sur CTRL + F5 pour exécuter le script.

Dans VS Code, générez le `Program.qs` pour la première fois en tapant le texte ci-dessous dans le terminal :

```Command line
dotnet build
```

Pour les exécutions suivantes, il n’est pas nécessaire de le regénérer. Pour l’exécuter, tapez la commande suivante et appuyez sur Entrée :

```Command line
dotnet run --no-build
```

Vous devriez voir le message suivant dans le terminal :

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

C’est parce que vous n’avez pas spécifié le nombre de qubits que vous vouliez utiliser, donc le terminal vous indique les commandes disponibles pour l’exécutable. Si nous souhaitons utiliser 5 qubits, nous devons taper :

```Command line
dotnet run --n-qubits 5
```

En appuyant sur Entrée, vous devriez normalement voir la sortie suivante :

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Étapes suivantes

Si ce tutoriel vous a plu, consultez certaines des ressources ci-dessous pour apprendre à utiliser le langage Q# afin d’écrire vos propres applications quantiques :

- [Retour au guide de démarrage avec le QDK](xref:microsoft.quantum.welcome)
- Essayer un [exemple](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) d’algorithme de recherche de Grover plus général
- [En savoir plus sur la recherche de Grover avec les katas quantiques](xref:microsoft.quantum.overview.katas)
- En savoir plus sur l’[amplification d’amplitude][amplitude-amplification], la technique d’informatique quantique derrière l’algorithme de recherche de Grover
- [Concepts de l’informatique quantique](xref:microsoft.quantum.concepts.intro)
- [Exemples du Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
