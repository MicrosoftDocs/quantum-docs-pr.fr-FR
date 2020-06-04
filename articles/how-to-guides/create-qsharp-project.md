---
title: 'Découvrez comment créer un projet Q # avec le kit de développement quantique (QDK)'
description: 'Initialiser un projet pour le développement quantique avec QDK et Q # dans l’environnement de développement de votre choix'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327524"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Créer un projet Q # dans votre environnement de développement

Découvrez comment créer un projet Q # avec QDK.

Un projet Q # contient des fichiers Q # contenant du code Quantum, ainsi qu’un programme hôte pour exécuter le programme Quantum. Vous pouvez écrire le programme hôte dans des langages .NET tels que C# ou dans Python. Vous pouvez également exécuter le code Q # dans un Jupyter Notebook à l’aide du noyau IQ #.

Choisissez votre environnement et votre langage de développement dans les sections ci-dessous :

* [Python](#create-a-python-project)
* [Notebooks Jupyter Q#](#create-a-q-jupyter-notebook-project)
* [C# avec Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C# avec VS Code](#create-a-c-project-using-vs-code)
* [C# avec la ligne de commande](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Créer un projet Python

1. Conditions préalables

     * Installer le [Kit de développement Quantum pour Python](xref:microsoft.quantum.install.python)

1. Créez un dossier pour votre projet et accédez à ce dossier

1. Créez un fichier Q # nommé `Operation.qs` et ajoutez-y votre code q #. Par exemple :

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

1. Créez un fichier d’hôte Python appelé `host.py` pour appeler votre opération Q #. Par exemple :

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

## <a name="create-a-q-jupyter-notebook-project"></a>Créer un projet Jupyter Notebook Q #

1. Conditions préalables

    * Installer le [Kit de développement quantique pour les blocs-notes Jupyter](xref:microsoft.quantum.install.jupyter)

1. Exécutez la commande suivante pour démarrer le serveur notebook :

    ```bash
    jupyter notebook
    ```

1. Accédez à l’URL affichée sur la ligne de commande. Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Une page Jupyter s’affiche dans le navigateur. Dans l’onglet **fichiers** , sélectionnez **nouveau**  >  **Q #** pour créer un Jupyter Notebook avec un noyau q #. Ajoutez le code suivant à la première cellule du bloc-notes :

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Sélectionnez **cellule**  >  **exécuter les cellules** pour exécuter le bloc-notes. `SayHello`s’affiche bientôt dans la sortie de la cellule :

    ![Jupyter Notebook cellule avec le code Q #](~/media/install-guide-jupyter.png)

    Lors de l’exécution dans des blocs-notes Jupyter, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.

1. Dans une nouvelle cellule, simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la commande magic `%simulate` :

    ![Jupyter Notebook cellule avec% simulateur magique](~/media/install-guide-jupyter-simulate.png)

    Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (vide dans ce cas).

Vous pouvez maintenant ajouter d’autres opérations Q # pour poursuivre le développement de votre Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Créer un projet C# sur Windows à l’aide de Visual Studio

1. Conditions préalables

    * Installer l' [extension du kit de développement Quantum pour Visual Studio](xref:microsoft.quantum.install.cs)

1. Créez une application en Q#

    * Accéder au **fichier**  ->  **nouveau**  ->  **projet**
    * Saisissez `Q#` dans la zone de recherche
    * Sélectionnez **Application Q#**
    * Sélectionnez **Suivant**.
    * Choisissez un nom et un emplacement pour votre application
    * Sélectionnez **Créer**

1. Examinez le projet

    Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.

1. Exécution de l'application

    * Sélectionnez **Déboguer**  ->  **exécuter sans débogage**
    * Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio

> [!NOTE]
> * Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  

## <a name="create-a-c-project-using-vs-code"></a>Créer un projet C#, à l’aide de VS Code

1. Conditions préalables

    * Installer l' [extension du kit de développement Quantum pour vs code](xref:microsoft.quantum.install.cs)

1. Créer un projet :

    * Accéder à **View**la  ->  **palette de commandes** de la vue
    * Sélectionnez **Q # : créer un projet**
    * Sélectionner une **application console autonome**
    * Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application
    * Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**

1. Exécutez l'application :

    * Accéder au **Terminal**  ->  **nouveau terminal**
    * Entrez `dotnet run`
    * Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`

Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio Code.

> [!NOTE]
> * Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Créer un projet C#, à l’aide de l' `dotnet` outil en ligne de commande

1. Conditions préalables

    * Installer le [Kit de développement Quantum pour la ligne de commande](xref:microsoft.quantum.install.standalone)

1. Créer une application

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Accédez au nouveau répertoire de l’application

    ```bash
    cd <project name>
    ```

    Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).

1. Exécution de l'application

    ```dotnetcli
    dotnet run
    ```

    Vous devez normalement voir la sortie suivante : `Hello quantum world!`

Vous continuez maintenant votre développement Quantum, à l’aide d’outils en ligne de commande.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez créé un projet dans votre environnement préféré, vous pouvez continuer votre développement quantique.
