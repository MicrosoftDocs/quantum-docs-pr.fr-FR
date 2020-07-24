---
title: Développer avec des applications en ligne de commande Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871431"
---
# <a name="develop-with-q-command-line-applications"></a>Développer avec des applications en ligne de commande Q#

Les programmes Q# peuvent être exécutés seuls et sans pilote dans un langage hôte comme C#, F# ou Python.

## <a name="prerequisites"></a>Prérequis

- [SDK .NET Core 3.1 ou ultérieur](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Bien que vous puissiez générer des applications en ligne de commande Q# dans n’importe quel IDE, nous vous recommandons d’utiliser l’IDE Visual Studio Code (VS Code) ou Visual Studio pour développer vos applications Q# localement. Pour le développement dans le cloud via le navigateur web, nous vous recommandons Visual Studio Codespaces. Lorsque vous développez dans ces environnements, vous pouvez tirer parti des nombreuses fonctionnalités de l’extension QDK, comme les avertissements, la coloration syntaxique, les modèles de projets, etc. 

Pour configurer VS Code :

1. Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).
2. Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Pour configurer Visual Studio :

1. Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.
2. Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Pour configurer Visual Studio Codespaces :

1. Créez un [compte Azure](https://azure.microsoft.com/free/).
2. Créez un environnement Codespaces. Suivez le [guide de démarrage rapide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser). Lorsque vous créez l’espace de code, nous vous recommandons d’entrer `microsoft/Quantum` dans le champ « Dépôt Git » pour charger les paramètres spécifiques au QDK.
3. Vous pouvez maintenant lancer votre nouvel environnement et commencer à développer dans le navigateur via l’[IDE cloud VS Codespaces](https://online.visualstudio.com/environments). Il est également possible d’utiliser votre installation locale de VS Code et d’utiliser Codespaces comme [environnement distant](https://docs.microsoft.com/visualstudio/online/how-to/vscode).


Si vous souhaitez installer le QDK pour un autre environnement, entrez ceci sur la ligne de commande :

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Développer avec Q#

Suivez les instructions situées sous l’onglet correspondant à votre environnement.

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

### <a name="other-editors-with-the-command-line"></a>[Autres éditeurs avec la ligne de commande](#tab/tabid-cmdline)

Vérifiez votre installation en créant une application `Hello World` Q#.

1. Installez les modèles de projet.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Créez une application :
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Accédez au répertoire de l’application :
    ```dotnetcli
    cd runSayHello
    ```

    Ce répertoire doit maintenant contenir un fichier `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console. Vous pouvez modifier ce modèle avec un éditeur de texte et le remplacer par vos propres applications quantiques. 

1. Exécutez le programme :
    ```dotnetcli
    dotnet run
    ```

1. Le texte suivant doit s’afficher : `Hello quantum world!`

***

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
