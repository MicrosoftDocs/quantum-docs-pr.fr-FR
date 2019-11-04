---
title: En savoir plus sur la mise à jour des Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463287"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Mettre à jour le Microsoft Quantum Development Kit (QDK)

Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.

Cet article suppose que vous avez déjà installé le QDK. Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Mise à jour des projets Q # 

1. Tout d’abord, installez la dernière version de la [kit SDK .NET Core 3,0](https://dotnet.microsoft.com/download) et exécutez la commande suivante à l’invite de commandes :
```bash
dotnet --version
```
 Vérifiez que la sortie est 3.0.100 ou supérieure, puis suivez les instructions ci-dessous en fonction de votre configuration.

### <a name="in-visual-studio"></a>Dans Visual Studio
 
 1. Mettez à jour vers la dernière version de Visual Studio 2019, voir [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pour obtenir des instructions
 2. Ouvrez votre solution dans Visual Studio
 3. Dans le menu, sélectionnez Générer > nettoyer la solution 
 4. [Mettre à jour le Framework cible](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) dans chacun de vos fichiers. csproj vers netcoreapp 3.0 (ou netstandard 2.1 s’il s’agit d’un projet de bibliothèque)
 5. Enregistrer et fermer tous les fichiers de votre solution
 6. Sélectionnez Outils > > de ligne de commande Invite de commandes développeur
 7. Pour chaque projet de la solution, exécutez la commande suivante :
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Si vos projets utilisent d’autres packages Microsoft. Quantum, exécutez la commande pour eux aussi. 
 8. Fermez l’invite de commandes et sélectionnez Générer > générer la solution (ne sélectionnez *pas* régénérer la solution, car la reconstruction échoue au départ)

### <a name="in-visual-studio-code"></a>Dans Visual Studio Code

1. Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour
1. Sélectionner terminal > nouveau terminal
1. Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande

### <a name="using-the-command-line"></a>À l’aide de la ligne de commande

1. Accédez au dossier contenant votre fichier projet
2. Exécutez la commande suivante :
```bash
dotnet clean [project_name].csproj
```

3. [Mettre à jour le Framework cible](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) dans chacun de vos fichiers. csproj vers netcoreapp 3.0 (ou netstandard 2.1 s’il s’agit d’un projet de bibliothèque)
4. Exécutez la commande suivante :
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Si votre projet utilise d’autres packages Microsoft. Quantum, exécutez la commande pour ceux-ci également.

5. Enregistrer et fermer tous les fichiers
6. Répétez 1-4 pour chaque dépendance de projet, puis revenez au dossier contenant votre projet principal et exécutez :
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Mettre à jour IQ # pour Python

1. Mettre à jour le noyau `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifier la version de `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Vous devez normalement voir la sortie suivante.

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. Mettre à jour le package `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Vérifier la version de `qsharp`

    ```bash
    pip show qsharp
    ```

    Vous devez normalement voir la sortie suivante.

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs`
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.

## <a name="update-iq-for-jupyter-notebooks"></a>Mettre à jour IQ # pour les blocs-notes Jupyter

1. Mettre à jour le noyau `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifier la version de `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Vous devez normalement voir la sortie suivante.

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :
    ```
    %workspace reload
    ```

1. Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.

## <a name="update-visual-studio-qdk-extension"></a>Mettre à jour l’extension QDK Visual Studio

1. Mettre à jour l’extension Q # Visual Studio

    - Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accepter la mise à jour

    > [!NOTE]
    > Les modèles de projet sont mis à jour avec l’extension. Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés. Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.

## <a name="update-vs-code-qdk-extension"></a>Mettre à jour VS Code extension QDK

1. Mettre à jour l’extension de VS Code Quantum

    - Redémarrer VS Code
    - Accédez à l’onglet **Extensions**
    - Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**
    - Recharger l’extension

1. Mettez à jour les modèles de projet Quantum :

   - Accédez à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q # : installer les modèles de projet**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, à l’aide de l’outil en ligne de commande `dotnet`

1. Mettre à jour les modèles de projet Quantum pour .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum. Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).
