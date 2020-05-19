---
title: 'Développer avec des blocs-notes Jupyter Q #'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551037"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Développer avec des blocs-notes Jupyter Q #

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


    - Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la `%simulate` commande :

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` , car notre opération retourne simplement un `Unit` type).

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
