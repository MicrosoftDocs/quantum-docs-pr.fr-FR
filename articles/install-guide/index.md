---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035303"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installer le Microsoft Quantum Development Kit (QDK)

Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique. Le QDK se compose des éléments suivants :

- le langage de programmation Q#
- un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#
- une application hôte (écrite en Python ou en langage .NET) qui exécute des opérations quantiques écrites en Q#
- des outils pour faciliter votre développement

Selon l’environnement de développement choisi, il existe différentes étapes d’installation. Choisissez votre environnement dans les sections ci-dessous.

## <a name="develop-with-python"></a>Développer avec Python

1. Conditions préalables

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [Kit SDK .NET Core 2.1 ou version ultérieure](https://www.microsoft.com/net/download)

1. Installez le package `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Installez le package `qsharp`

    ```bash
    pip install qsharp
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

1. Conditions préalables

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 2.1 ou version ultérieure](https://www.microsoft.com/net/download)

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

        ![Cellule du notebook Jupyter](~/media/install-guide-jupyter.png)

        Vous devriez voir `SayHello` dans la sortie de la cellule. Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Développer en C# sur Windows, à l’aide de Visual Studio

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

## <a name="develop-with-c-using-vs-code"></a>Développer en C#, à l’aide de VS Code

1. Conditions préalables

   - [Code Visual Studio](https://code.visualstudio.com/download)
   - [Kit SDK .NET Core 2.1 ou version ultérieure](https://www.microsoft.com/net/download)

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

1. Conditions préalables

    - [Kit SDK .NET Core 2.1 ou version ultérieure](https://www.microsoft.com/net/download)

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
