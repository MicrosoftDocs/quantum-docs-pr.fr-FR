---
title: 'Développer avec les applications en ligne de commande Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426438"
---
# <a name="develop-with-q-command-line-applications"></a>Développer avec les applications en ligne de commande Q #

Les programmes Q # peuvent être exécutés seuls, sans pilote dans un langage hôte tel que C#, F # ou python.

## <a name="pre-requisites"></a>Conditions préalables

- [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Bien que vous puissiez générer des applications en ligne de commande Q # dans n’importe quel IDE, nous vous recommandons d’utiliser Visual Studio Code (VS Code) ou IDE de Visual Studio pour vos applications Q #. Le développement de ces outils permet d’accéder à des fonctionnalités riches.

Pour configurer VS Code :

1. Téléchargez et installez [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac).
2. Installez [Microsoft QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Pour configurer Visual Studio :

1. Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 ou version ultérieure, avec la charge de travail développement multiplateforme .net Core activée.
2. Téléchargez et installez [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Développer avec Q # à l’aide de VS Code

Installez les modèles de projet Q # :

1. Ouvrez Visual Studio Code.
2. Cliquez sur **Afficher**la  ->  **palette de commandes**.
3. Sélectionnez **Q # : installer les modèles de projet**.

Lorsque les **modèles de projet installés avec succès** s’affichent, le QDK est prêt à être utilisé avec vos propres applications et bibliothèques.

Pour créer un nouveau projet :

1. Cliquez sur **Afficher**la  ->  **palette de commandes** et sélectionnez **Q # : créer un projet**.
2. Cliquez sur **application console autonome**.
3. Accédez à l’emplacement où enregistrer le projet, puis cliquez sur **créer un projet**.
4. Lorsque le projet est correctement créé, cliquez sur **ouvrir le nouveau projet...** dans le coin inférieur droit.
        
Inspectez le projet. Vous devez voir un fichier source nommé `Program.qs` , qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.

Pour exécuter l’application :
1. Cliquez sur **Terminal**  ->  **nouveau terminal**.
2. À l’invite du terminal, entrez `dotnet run` .
3. Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`


> [!NOTE]
> Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension VS Code Q #. Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.

## <a name="develop-with-q-using-visual-studio"></a>Développer avec Q # à l’aide de Visual Studio

Vérifiez votre installation de Visual Studio en créant une application Q # `Hello World` .

Pour créer une nouvelle application Q # :
1. Ouvrez Visual Studio et cliquez sur **fichier**  ->  **nouveau**  ->  **projet**.
2. Tapez `Q#` dans la zone de recherche, sélectionnez **Q # application** , puis cliquez sur **suivant**.
3. Entrez un nom et un emplacement pour votre application, puis cliquez sur **créer**.


Inspectez le projet. Vous devez voir un fichier source nommé `Program.qs` , qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.

Pour exécuter l’application :
1. Sélectionnez **Déboguer**  ->  **exécuter sans débogage**.
2. Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.

> [!NOTE]
> Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans l’un de ses sous-dossiers.  


## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
