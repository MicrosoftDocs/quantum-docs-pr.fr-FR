---
title: 'Découvrez comment créer un projet Q # avec le kit de développement quantique (QDK)'
description: 'Initialiser un projet pour le développement quantique avec QDK et Q # dans l’environnement de développement de votre choix'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444172"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Créer un projet Q # dans votre environnement de développement

Découvrez comment créer un projet Q # avec QDK.

Un projet Q # contient des fichiers Q # contenant du code Quantum, ainsi qu’un programme hôte pour exécuter le programme Quantum. Vous pouvez écrire le programme hôte dans des langages .NET C#tels que, ou dans Python. Vous pouvez également exécuter le code Q # dans un bloc-notes Jupyter à l’aide du noyau IQ #.

Choisissez votre environnement et votre langage de développement dans les sections ci-dessous :

* [Python](#create-a-python-project)
* [Blocs-notes Jupyter](#create-a-jupyter-notebook-project)
* [C#avec Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#avec VS Code](#create-a-c-project-using-vs-code)
* [C#avec la ligne de commande](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Créer un projet python

1. Prérequis

     * [Kit de développement quantique pour Python](xref:microsoft.quantum.install#develop-with-python)

1. Créez un dossier pour votre projet et accédez à ce dossier

1. Créez un fichier Q # nommé `Operation.qs`et ajoutez-y votre code Q #. Exemple :

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Créez un fichier d’hôte Python appelé `host.py` pour appeler votre opération Q #. Exemple :

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Exécutez le programme :

    ```bash
    python host.py
    ```

1. Vérifiez la sortie. Votre programme doit générer les lignes suivantes :

    ```bash
    Hello from quantum world!
    0
    ```

Vous pouvez maintenant continuer à développer votre programme Quantum.

## <a name="create-a-jupyter-notebook-project"></a>Créer un projet Jupyter Notebook

1. Prérequis

    * Le [Kit de développement quantique pour les blocs-notes Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Exécutez la commande suivante pour démarrer le serveur notebook :

    ```bash
    jupyter notebook
    ```

1. Accédez à l’URL affichée sur la ligne de commande. Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Une page Jupyter s’affiche dans le navigateur. Dans l’onglet **fichiers** , sélectionnez **nouveau** > **Q #** pour créer un bloc-notes Jupyter avec un noyau q #. Ajoutez le code suivant à la première cellule du bloc-notes :

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Sélectionnez **cellule** > **exécuter les cellules** pour exécuter le bloc-notes. `SayHello` s’affiche bientôt dans la sortie de la cellule :

    ![Jupyter cellule de bloc-notes avec le code Q #](~/media/install-guide-jupyter.png)

    Lors de l’exécution dans des blocs-notes Jupyter, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.

1. Dans une nouvelle cellule, Simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la `%simulate` Magic :

    ![Cellule de bloc-notes Jupyter avec% simuler Magic](~/media/install-guide-jupyter-simulate.png)

    Vous devez voir le message imprimé à l’écran, ainsi que le résultat de l’opération que vous avez appelée (dans ce cas, vide).

Vous pouvez maintenant ajouter d’autres opérations Q # pour poursuivre le développement de votre Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Créer un C# projet sur Windows à l’aide de Visual Studio

1. Prérequis

    * Le [Kit de développement quantique pour Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Créez une application en Q#

    * Accédez à **Fichier** -> **Nouveau** -> **Projet**
    * Saisissez `Q#` dans la zone de recherche
    * Sélectionnez **Application Q#**
    * Sélectionnez **Suivant**.
    * Choisissez un nom et un emplacement pour votre application
    * Sélectionnez **Créer**

1. Examinez le projet

    Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.

1. Exécution de l’application

    * Sélectionnez **Débogage** -> **Démarrer sans débogage**
    * Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio

> [!NOTE]
> * Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  

## <a name="create-a-c-project-using-vs-code"></a>Créer un C# projet à l’aide de vs code

1. Prérequis

    * [Kit de développement quantique pour vs code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Créer un projet :

    * Accédez à **Affichage** -> **Palette de commandes**
    * Sélectionnez **Q # : créer un projet**
    * Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application
    * Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**

1. Exécutez l'application :

    * Accédez à **Débogage** -> **Démarrer sans débogage**
    * Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`

Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio Code.

> [!NOTE]
> * Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Créer un C# projet à l’aide de l’outil en ligne de commande `dotnet`

1. Prérequis

    * [Kit de développement quantique pour la ligne de commande](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Créer une application

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Accédez au nouveau répertoire de l’application

    ```bash
    cd <project name>
    ```

    Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).

1. Exécution de l’application

    ```bash
    dotnet run
    ```

    Vous devez normalement voir la sortie suivante : `Hello quantum world!`

Vous continuez maintenant votre développement Quantum, à l’aide d’outils en ligne de commande.

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez créé un projet dans votre environnement préféré, vous pouvez continuer votre développement quantique.