---
title: Développer avec des notebooks Jupyter Q#
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274096"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Développer avec des notebooks Jupyter Q#

Installez le QDK pour le développement d’opérations Q# sur des notebooks Jupyter Q#

Les notebooks Jupyter permettent l’exécution de code sur place aux côtés d’instructions, de notes et d’autres contenus. Cet environnement est idéal pour écrire du code Q# avec des explications incorporées ou des tutoriels interactifs sur l’informatique quantique. Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

> [!NOTE]
> * Dans les notebooks Jupyter Q#, vous pouvez uniquement exécuter du code Q# et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, des fichiers Python ou C#). Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme quantique.

1. Prérequis

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installez le package `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.
    > Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.
    > En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.

1. Vérifiez l’installation en créant une application `Hello World`

    - Exécutez la commande suivante pour démarrer le serveur notebook :

        ```
        jupyter notebook
        ```

    - Pour ouvrir le notebook Jupyter, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.

    - Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Exécutez cette cellule du notebook :

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        Vous devriez voir `SayHello` dans la sortie de la cellule. Lors de l’exécution dans un notebook Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.


    - Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` car notre opération retourne simplement un type `Unit`).

## <a name="next-steps"></a>Étapes suivantes

Une fois le QDK installé pour les notebooks Jupyter Q#, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng) en écrivant votre code Q# directement dans l’environnement Jupyter Notebook.

Pour obtenir plus d’exemples de ce que vous pouvez faire avec des notebooks Jupyter Q#, consultez les rubriques suivantes :
- [Présentation de Q# et de Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) Vous trouverez ici un notebook Jupyter Q# qui montre comment utiliser Q# dans cet environnement.
- [Katas Quantum](xref:microsoft.quantum.overview.katas), une collection open source de tutoriels auto-rythmés et d’exercices de programmation sous la forme de notebooks Jupyter Q#. Les [notebooks des katas Quantum](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ. Les katas Quantum sont conçus pour vous inculquer des notions de l’informatique quantique et de la programmation en Q#. Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des notebooks Jupyter Q#.
