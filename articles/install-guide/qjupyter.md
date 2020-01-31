---
title: 'Développer avec des blocs-notes Jupyter Q #'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831067"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Développer avec des blocs-notes Jupyter Q #

Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.

Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus. Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing. Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

> [!NOTE]
> * Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir C# de programmes hôtes externes (par exemple, Python ou fichiers). Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.

1. Prérequis

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)

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

    - Pour ouvrir le bloc-notes Jupyter, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.

    - Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Exécutez cette cellule du notebook :

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        Vous devriez voir `SayHello` dans la sortie de la cellule. Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.


    - Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` parce que notre opération retourne simplement un type de `Unit`).

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).
