---
title: 'Exécuter les programmes Q # sans pilote ni langue hôte'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706799"
---
# <a name="q-command-line-applications"></a>Q # applications en ligne de commande

Les programmes Q # peuvent être exécutés seuls, sans pilote dans un langage hôte tel que C#, F # ou python.

## <a name="pre-requisites"></a>Conditions préalables

- [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Bien que vous puissiez créer des applications en ligne de commande Q # dans n’importe quel IDE, nous vous recommandons vivement d’utiliser Visual Studio Code (VS Code) ou l’IDE de Visual Studio pour vos applications Q #. En utilisant VS Code ou Visual Studio et l’extension QDK Visual Studio Code vous accédez à des fonctionnalités plus riches.

- Installer [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac)
- Installez l' [extension QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) ou
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée
- Télécharger et installer l' [extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Développer avec Q # à l’aide de VS Code

Installez les modèles de projet Quantum :

- Accéder à la**palette de commandes** de la **vue** -> 
- Sélectionnez **Q # : installer les modèles de projet**

Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.
- Créer un projet :
  - Accéder à la**palette de commandes** de la **vue** -> 
  - Sélectionnez **Q # : créer un projet**
  - Sélectionner une **application console autonome**
  - Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application
  - Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**
        
- Examinez le projet
  - Vous devez voir un fichier appelé `Program.qs` créé, qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.

- Exécutez l'application :
  - Accéder au **Terminal** -> **nouveau terminal**
  - Entrez `dotnet run`
  - Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`


> [!NOTE]
> * Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## <a name="develop-with-q-using-visual-studio"></a>Développer avec Q # à l’aide de Visual Studio

Vérifiez l’installation en créant une application `Hello World`

- Créez une application en Q#
  - Accéder au **fichier** -> **nouveau** -> **projet**
  - Saisissez `Q#` dans la zone de recherche
  - Sélectionnez **Application Q#**
  - Sélectionnez **Suivant**.
  - Choisissez un nom et un emplacement pour votre application
  - Sélectionnez **Créer**

- Examinez le projet
  - Vous devez voir qu’un fichier appelé `Program.qs` a été créé, qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.

- Exécution de l'application
  - Sélectionnez **Déboguer** -> **exécuter sans débogage**
  - Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

> [!NOTE]
> * Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  


## <a name="whats-next"></a>Quelle est l’étape suivante ?

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).
