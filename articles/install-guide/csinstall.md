---
title: 'Développer avec Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831016"
---
# <a name="develop-with-q--c"></a>Développer avec Q # +C#

Installez le QDK pour développer C# des programmes hôtes afin d’appeler des opérations Q #.

Q # est conçu pour fonctionner correctement avec les langages .NET, C#en particulier. Vous pouvez utiliser ce couplage dans différents environnements de développement :

- [Q # + C# utilisation de Visual Studio (Windows)](#VS)
- [Q # + C# utilisation de Visual Studio code (Windows, Linux et Mac)](#VSC)
- [Q # + C# utilisation de l’outil de ligne de commande `dotnet`](#command)

## Développer avec Q # + C# à l’aide de Visual Studio<a name="VS"></a>

Visual Studio offre un environnement riche pour le développement de programmes Q #. L’extension Q # Visual Studio contient des modèles pour les fichiers et projets Q #, ainsi que la mise en surbrillance de la syntaxe, la saisie semi-automatique du code et la prise en charge IntelliSense.


1. Prérequis

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée

1. Installez l’extension Visual Studio pour Q#

    - Télécharger et installer l' [extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Développer avec Q # + C# à l’aide de Visual Studio code<a name="VSC"></a>

Visual Studio Code (VS Code) offre un environnement riche pour le développement de programmes Q # sur Windows, Linux et Mac.  L’extension Q # VS Code prend en charge la mise en surbrillance de la syntaxe Q #, la saisie semi-automatique du code et les extraits de code Q #.

1. Prérequis

   - [Code Visual Studio](https://code.visualstudio.com/download)
   - [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)

1. Installez l’extension VS Code pour Quantum

    - Installez [l’extension VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installez les modèles de projet Quantum :

   - Accédez à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q # : installer les modèles de projet**

    Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.

1. Vérifiez l’installation en créant une application `Hello World`

    - Créer un projet :

        - Accédez à **Affichage** -> **Palette de commandes**
        - Sélectionnez **Q # : créer un projet**
        - Sélectionner une **application console autonome**
        - Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application
        - Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**

    - Si vous n’avez pas encore C# l’extension pour vs code installée, une fenêtre contextuelle s’affiche. Installez l’extension. 

    - Exécutez l'application :

        - Accéder au **terminal** -> **nouveau terminal**
        - Entrez `dotnet run`
        - Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`


> [!NOTE]
> * Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## Développer avec Q # + C# à l’aide de l’outil de ligne de commande `dotnet`<a name="command"></a>

Bien entendu, vous pouvez également générer et exécuter des programmes Q# à partir de la ligne de commande en installant simplement le SDK .NET Core et les modèles de projet QDK. 

1. Prérequis

    - [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)

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
