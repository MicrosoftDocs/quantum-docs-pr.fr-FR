---
title: Développer avec des applications en ligne de commande Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274121"
---
# <a name="develop-with-q-command-line-applications"></a>Développer avec des applications en ligne de commande Q#

Les programmes Q# peuvent être exécutés seuls et sans pilote dans un langage hôte comme C#, F# ou Python.

## <a name="prerequisites"></a>Prérequis

- [SDK .NET Core 3.1 ou ultérieur](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Bien que vous puissiez générer des applications en ligne de commande Q# dans n’importe quel IDE, nous vous recommandons d’utiliser Visual Studio Code (VS Code) ou Visual Studio IDE pour vos applications Q#. Le développement dans ces outils vous donne accès à de riches fonctionnalités.

Pour configurer VS Code :

1. Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).
2. Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Pour configurer Visual Studio :

1. Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.
2. Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Développer en Q# à l’aide de VS Code

Installez les modèles de projet Q# :

1. Ouvrez Visual Studio Code.
2. Cliquez sur **Affichage** -> **Palette de commandes**.
3. Sélectionnez **Q# : Installer des modèles de projet**.

Quand **Modèles de projet installés** s’affiche, le QDK est prêt à être utilisé avec vos propres applications et bibliothèques.

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

## <a name="develop-with-q-using-visual-studio"></a>Développer en Q# avec Visual Studio

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


## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
