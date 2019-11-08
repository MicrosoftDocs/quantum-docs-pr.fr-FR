---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799166"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installer le Microsoft Quantum Development Kit (QDK)

Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique. Le QDK se compose des éléments suivants :

- le langage de programmation Q#
- un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#
- une application hôte (écrite en Python ou en langage .NET) qui exécute des opérations quantiques écrites en Q#
- des outils pour faciliter votre développement

Selon l’environnement de développement choisi, il existe différentes étapes d’installation. Choisissez votre environnement dans les sections ci-dessous.

## <a name="develop-with-python"></a>Développer avec Python

Le package qsharp pour Python facilite la simulation des opérations et des fonctions Q# dans Python. IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

1. Conditions préalables

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK .NET Core 3.0 ou ultérieur](https://www.microsoft.com/net/download)

1. Installez le package `qsharp`

    ```bash
    pip install qsharp
    ```

1. Installez le package `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifiez l’installation en créant une application `Hello World`

    - Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Exécutez le programme :

        ```bash
        python hello_world.py
        ```

    - Vérifiez la sortie. Votre programme doit générer les lignes suivantes :

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Développer avec des notebooks Jupyter

Particulièrement appréciés des universités, laboratoires scientifiques et structures de programmation collaborative en ligne, les notebooks Jupyter assurent l’exécution de code sur place (y compris, désormais, du code Q#) et permettent d’utiliser des instructions, des notes et d’autres contenus.  Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.


1. Conditions préalables

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK .NET Core 3.0 ou ultérieur](https://www.microsoft.com/net/download)

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

    - Accédez à l’URL affichée sur la ligne de commande. Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Exécutez cette cellule du notebook :

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        Vous devriez voir `SayHello` dans la sortie de la cellule. Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.


    - Dans une nouvelle cellule, simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la commande magic `%simulate` :

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (vide dans ce cas).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Développer en C# sur Windows, à l’aide de Visual Studio

Visual Studio offre un environnement complet pour le développement de programmes Q# et notamment de puissantes fonctionnalités telles que la complétion de code et la mise en surbrillance de la syntaxe, qui guident le développeur dans la création d’applications.  L’extension Visual Studio Q# propose des modèles pour les fichiers et projets Q#, ainsi que la mise en surbrillance de la syntaxe et la prise en charge d’IntelliSense.


1. Conditions préalables

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée

1. Installez l’extension Visual Studio pour Q#

    - Téléchargez l’[extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Ajoutez l’extension à Visual Studio

1. Vérifiez l’installation en créant une application `Hello World`

    - Créez une application en Q#

        - Accédez à **Fichier** -> **Nouveau** -> **Projet**
        - Saisissez `Q#` dans la zone de recherche
        - Sélectionnez **Application Q#**
        - Sélectionnez **Suivant**.
        - Choisissez un nom et un emplacement pour votre application
        - Sélectionnez **Créer**

    - Examinez le projet

        Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.

    - Exécution de l'application

        - Sélectionnez **Débogage** -> **Démarrer sans débogage**
        - Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

> [!NOTE]
> * Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  

## <a name="develop-with-c-using-visual-studio-code"></a>Développer en C# avec Visual Studio Code

Visual Studio Code (VS Code) apporte un environnement complet pour le développement de programmes Q# dans de nombreux environnements informatiques, notamment Windows, Linux et Mac. Il offre de puissantes fonctionnalités telles que la complétion de code et la mise en surbrillance de la syntaxe, qui guident le développeur dans la création d’applications.  L’extension VS Code Q# assure la mise en surbrillance de la syntaxe et offre des extraits de code Q#.

1. Conditions préalables

   - [Code Visual Studio](https://code.visualstudio.com/download)
   - [SDK .NET Core 3.0 ou ultérieur](https://www.microsoft.com/net/download)

1. Installez l’extension VS Code pour Quantum

    - Installez [l’extension VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installez les modèles de projet Quantum :

   - Accédez à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q# : Installer des modèles de projet**

    Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.

1. Vérifiez l’installation en créant une application `Hello World`

    - Créer un projet :

        - Accédez à **Affichage** -> **Palette de commandes**
        - Sélectionnez **Q# : Créer un projet**
        - Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application
        - Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**

    - Exécutez l'application :

        - Accédez à **Débogage** -> **Démarrer sans débogage**
        - Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`

> [!NOTE]
> * > * Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Développer en C#, à l’aide du programme en ligne de commande `dotnet`

Bien entendu, vous pouvez également générer et exécuter des programmes Q# à partir de la ligne de commande en installant simplement le SDK .NET Core et les modèles de projet QDK. 

1. Conditions préalables

    - [SDK .NET Core 3.0 ou ultérieur](https://www.microsoft.com/net/download)

1. Installez les modèles de projet Quantum pour .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.

1. Vérifiez l’installation en créant une application `Hello World`

    - Créer une application

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Accédez au nouveau répertoire de l’application

       ```bash
       cd runSayHello
       ```

    Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).

    - Exécution de l'application

        ```bash
        dotnet run
        ```

        Vous devez normalement voir la sortie suivante : `Hello quantum world!`

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).
