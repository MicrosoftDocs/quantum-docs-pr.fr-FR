---
title: Développer avec Q# + Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630333"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Développer avec Q# + Jupyter Notebook

Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.

Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus. Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing. Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

> [!NOTE]
> * Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, fichiers python ou C#). Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.

1. Prérequis

    - [Python](https://www.python.org/downloads/) 3,6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installez le package `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Si vous recevez une erreur lors de l' `dotnet iqsharp install` étape, ouvrez une nouvelle fenêtre de terminal, puis réessayez.
    > Si cela ne fonctionne toujours pas, essayez de localiser l' `dotnet-iqsharp` outil installé (sur Windows `dotnet-iqsharp.exe` ) et d’exécuter :
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin d’accès absolu à l' `dotnet-iqsharp` outil dans votre système de fichiers.
    > En général, il se trouve sous `.dotnet/tools` dans votre dossier de profil utilisateur.

1. Vérifiez l’installation en créant une application `Hello World`

    - Exécutez la commande suivante pour démarrer le serveur notebook :

        ```
        jupyter notebook
        ```

    - Pour ouvrir la Jupyter Notebook, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.

    - Créez un Jupyter Notebook avec un noyau Q #, puis ajoutez le code suivant à la première cellule du bloc-notes :

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Exécutez cette cellule du notebook :

        ![Jupyter Notebook cellule avec le code Q #](~/media/install-guide-jupyter.png)

        Vous devriez voir `SayHello` dans la sortie de la cellule. En cas d’exécution dans Jupyter Notebook, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.


    - Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la `%simulate` commande :

        ![Jupyter Notebook cellule avec% simulateur magique](~/media/install-guide-jupyter-simulate.png)

        Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` , car notre opération retourne simplement un `Unit` type).

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le QDK pour les blocs-notes Q # Jupyter, vous pouvez écrire et exécuter [votre premier programme Quantum](xref:microsoft.quantum.quickstarts.qrng) en écrivant votre code Q # directement dans l’environnement de Jupyter Notebook.

Pour obtenir plus d’exemples de ce que vous pouvez faire avec les blocs-notes Jupyter Q #, consultez :
- [Introduction à Q # et Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Vous y trouverez une Jupyter Notebook Q # qui montre comment utiliser Q # dans cet environnement.
- [Quantum katas](xref:microsoft.quantum.overview.katas), une collection Open source de didacticiels à votre rythme et de jeux d’exercices de programmation sous la forme de blocs-notes Q # Jupyter. Les [blocs-notes Quantum katas Tutorial](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ. Les katas Quantum visent à vous enseigner des éléments de quantum computing et Q # Programming en même temps. Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des blocs-notes Q # Jupyter.
