---
title: Développer avec Q# + Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660758"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Développer avec Q# + Jupyter Notebook

Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.

Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus. Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing. Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

> [!NOTE]
> * Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, fichiers python ou C#). Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.

1. Conditions préalables

    - [Python](https://www.python.org/downloads/) 3,6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installez le package `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifiez l’installation en créant une application `Hello World`

    - Exécutez la commande suivante pour démarrer le serveur notebook :

        ```bash
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
