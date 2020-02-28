---
title: En savoir plus sur la mise à jour des Microsoft Quantum Development Kit (QDK)
description: 'Décrit comment mettre à jour vos projets Q # et le Microsoft Quantum Development Kit à la version actuelle.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 264b5640216b2c0a468b625cdef4b9e0123d8b39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904755"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Mettre à jour le Microsoft Quantum Development Kit (QDK)

Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.

Cet article suppose que vous avez déjà installé le QDK. Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).

Nous vous recommandons de rester à jour avec la dernière version de QDK. Suivez ce guide de mise à jour pour effectuer une mise à niveau vers la version la plus récente de QDK. Le processus se compose de deux parties :
1. mise à jour de vos projets et fichiers Q # existants afin d’aligner votre code avec toute syntaxe mise à jour
2. mise à jour du QDK lui-même pour l’environnement de développement choisi 

## <a name="updating-q-projects"></a>Mise à jour des projets Q # 

Que vous utilisiez C# ou python pour héberger des opérations q #, suivez ces instructions pour mettre à jour vos projets q #.

1. Tout d’abord, vérifiez que vous disposez de la dernière version de la [kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download). Exécutez la commande suivante à l’invite de commandes :

    ```dotnetcli
    dotnet --version
    ```

    Vérifiez que la sortie est `3.1.100` ou supérieure. Si ce n’est pas le cas, installez la [version la plus récente](https://dotnet.microsoft.com/download) et vérifiez à nouveau. Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement la ligne de commande).

### <a name="update-q-projects-in-visual-studio"></a>Mettre à jour les projets Q # dans Visual Studio
 
1. Mettez à jour vers la dernière version de Visual Studio 2019, voir [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pour obtenir des instructions
2. Ouvrez votre solution dans Visual Studio
3. Dans le menu, sélectionnez **générer** -> **nettoyer la solution**
4. Dans chacun de vos fichiers. csproj, mettez à jour la version cible de .NET Framework pour `netcoreapp3.0` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).
    Autrement dit, modifiez les lignes du formulaire :

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Enregistrer et fermer tous les fichiers de votre solution
6. Sélectionnez **outils** ->  -> de **ligne de commande** **invite de commandes développeur**
7. Pour chaque projet de la solution, exécutez la commande suivante :

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Si vos projets utilisent d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.
8. Fermez l’invite de commandes et sélectionnez **générer** -> **générer la solution** (ne sélectionnez *pas* régénérer la solution)

Vous pouvez maintenant passer directement à [la mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Mettre à jour les projets Q # dans Visual Studio Code

1. Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour
2. Sélectionner **terminal** -> **nouveau terminal**
3. Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande (directement ci-dessous)

### <a name="update-q-projects-using-the-command-line"></a>Mettre à jour les projets Q # à l’aide de la ligne de commande

1. Accédez au dossier contenant votre fichier projet
2. Exécutez la commande suivante :

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Dans chacun de vos fichiers. csproj, mettez à jour la version cible de .NET Framework pour `netcoreapp3.0` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).
    Autrement dit, modifiez les lignes du formulaire :

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Exécutez la commande suivante :

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Si votre projet utilise d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.
5. Enregistrez et fermez tous les fichiers.
6. Répétez 1-4 pour chaque dépendance de projet, puis revenez au dossier contenant votre projet principal et exécutez :

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Une fois vos projets Q # mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK lui-même.

## <a name="updating-the-qdk"></a>Mise à jour de QDK

Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.
Sélectionnez votre environnement de développement ci-dessous.

* [Python : mettre à jour l’extension IQ #](#update-iq-for-python)
* [Blocs-notes Jupyter : mettre à jour l’extension IQ #](#update-iq-for-jupyter-notebooks)
* [Visual Studio : mettre à jour l’extension QDK](#update-visual-studio-qdk-extension)
* [VS Code : mettre à jour l’extension QDK](#update-vs-code-qdk-extension)
* [Ligne de commande et C#: mettre à jour les modèles de projet](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Mettre à jour IQ # pour Python

1. Mettre à jour le noyau `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Vérifier la version de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Vous devez normalement voir la sortie suivante.

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, elle doit correspondre à la version la [plus récente](xref:microsoft.quantum.relnotes).

3. Mettre à jour le package `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

4. Vérifier la version de `qsharp`

    ```bash
    pip show qsharp
    ```

    Vous devez normalement voir la sortie suivante.

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.

### <a name="update-iq-for-jupyter-notebooks"></a>Mettre à jour IQ # pour les blocs-notes Jupyter

1. Mettre à jour le noyau `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Vérifier la version de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Le résultat doit ressembler à ce qui suit :

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, elle doit correspondre à la version la [plus récente](xref:microsoft.quantum.relnotes).

3. Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :

    ```
    %workspace reload
    ```

4. Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.

### <a name="update-visual-studio-qdk-extension"></a>Mettre à jour l’extension QDK Visual Studio

1. Mettre à jour l’extension Q # Visual Studio

    - Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accepter la mise à jour

    > [!NOTE]
    > Les modèles de projet sont mis à jour avec l’extension. Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés. Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.

### <a name="update-vs-code-qdk-extension"></a>Mettre à jour VS Code extension QDK

1. Mettre à jour l’extension de VS Code Quantum

    - Redémarrer VS Code
    - Accédez à l’onglet **Extensions**
    - Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**
    - Recharger l’extension

2. Mettez à jour les modèles de projet Quantum :

   - Accédez à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q # : installer les modèles de projet**
   - Après quelques secondes, vous devriez obtenir un message contextuel « les modèles de projet ont été installés avec succès »

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, à l’aide de l’outil en ligne de commande `dotnet`

1. Mettre à jour les modèles de projet Quantum pour .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Quelle est l’étape suivante ?

Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum. Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).
