---
title: Développer avec des applications Q# dans un IDE
description: Découvrez comment créer une application Q# qui s’exécute à partir de l’invite de commandes.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376420"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Développer avec des applications Q# dans un IDE

Les programmes Q# peuvent s’exécuter seuls et sans pilote dans un langage hôte comme C#, F# ou Python. Vous pouvez développer des applications Q# dans Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, ou avec n’importe quel éditeur/IDE et exécuter des applications à partir de la console .NET. 

## <a name="prerequisites-for-all-environments"></a>Prérequis pour tous les environnements

- [SDK .NET Core 3.1 ou ultérieur](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Même si vous pouvez générer des applications Q# dans n’importe quel IDE, nous vous recommandons d’utiliser l’IDE Visual Studio Code (VS Code) ou Visual Studio pour développer vos applications Q# localement. Pour le développement dans le cloud via le navigateur web, nous vous recommandons Visual Studio Codespaces. Lorsque vous développez dans ces environnements, vous pouvez tirer parti des nombreuses fonctionnalités de l’extension QDK, comme les avertissements, la coloration syntaxique, les modèles de projets, etc. 

### <a name="to-configure-for-vs-code"></a>Pour configurer pour VS Code :

1. Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).
2. Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Pour configurer pour Visual Studio :

1. Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.
2. Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Pour configurer pour un autre environnement : 

1. À l’invite de commandes, entrez ce qui suit :

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Pour configurer pour Visual Studio Codespaces :

1. Créez un [compte Azure](https://azure.microsoft.com/free/).
2. Créez un environnement Codespaces. Suivez le [guide de démarrage rapide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). Lorsque vous créez l’espace de code, nous vous recommandons d’entrer `microsoft/Quantum` dans le champ « Dépôt Git » pour charger les paramètres spécifiques au QDK.
3. Vous pouvez maintenant lancer votre nouvel environnement et commencer à développer dans le navigateur via l’[IDE cloud VS Codespaces](https://online.visualstudio.com/environments). Il est également possible d’utiliser votre installation locale de VS Code et d’utiliser Codespaces comme [environnement distant](https://docs.microsoft.com/visualstudio/online/how-to/vscode).

## <a name="develop-with-no-locq"></a>Développer avec Q#

Suivez les instructions sous l’onglet correspondant à votre environnement de développement.

### <a name="vs-code"></a>[Code Visual Studio](#tab/tabid-vscode)

Pour créer un projet :

1. Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet**.
2. Cliquez sur **Application console autonome**.
3. Accédez à l’emplacement où vous souhaitez enregistrer le projet, puis cliquez sur **Créer le projet**.
4. Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.

Examinez le projet. Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.

Pour exécuter l’application :

1. Cliquez sur **Terminal** -> **Nouveau terminal**.
2. À l’invite du terminal, entrez `dotnet run`.
3. Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`

> [!NOTE]
> Les espaces de travail avec plusieurs dossiers racine ne sont pas actuellement pris en charge par l’extension VS Code Q#. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Vérifiez votre installation de Visual Studio en créant une application Q# `Hello World`.

Pour créer une application Q# :

1. Ouvrez Visual Studio, puis cliquez sur **Fichier** -> **Nouveau** -> **Projet**.
2. Tapez `Q#` dans la zone de recherche, sélectionnez **Application Q#** , puis cliquez sur **Suivant**.
3. Entrez un nom et un emplacement pour votre application, puis cliquez sur **Créer**.


Examinez le projet. Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.

Pour exécuter l’application :

1. Sélectionnez **Déboguer** -> **Démarrer sans débogage**
2. Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

> [!NOTE]
> Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  

### <a name="other-editors-with-the-command-prompt"></a>[Autres éditeurs avec l’invite de commandes](#tab/tabid-cmdline)

Vérifiez votre installation en créant une application Q# `Hello World`.

1. Créez une application :

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Accédez au répertoire de l’application :

    ```dotnetcli
    cd runSayHello
    ```

    Ce répertoire doit maintenant contenir un fichier `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console. Vous pouvez modifier ce modèle avec un éditeur de texte et le remplacer par vos propres applications quantiques. 

1. Exécutez le programme :

    ```dotnetcli
    dotnet run
    ```

1. Le texte suivant doit s’afficher : `Hello quantum world!`

***

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
