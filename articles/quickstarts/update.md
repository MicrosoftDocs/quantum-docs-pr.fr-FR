---
title: Mettre à jour le Quantum Development Kit (QDK)
description: Décrit comment mettre à jour vos projets Q# et le Microsoft Quantum Development Kit avec la version actuelle.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274046"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Mettre à jour le Microsoft Quantum Development Kit (QDK)

Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) avec la dernière version.

Cet article suppose que vous avez déjà installé le QDK. Si vous effectuez l’installation pour la première fois, consultez le [guide d’installation](xref:microsoft.quantum.install).

Nous vous recommandons d’utiliser la dernière version du QDK. Suivez ce guide de mise à jour pour effectuer la mise à niveau vers la dernière version du QDK. Le processus se compose de deux parties :
1. Mise à jour de vos fichiers et projets Q# existants afin d’aligner votre code avec toute syntaxe mise à jour.
2. Mise à jour du QDK à proprement dit pour l’environnement de développement choisi.

## <a name="updating-q-projects"></a>Mise à jour des projets Q# 

Que vous utilisiez C# ou Python pour héberger des opérations Q#, suivez ces instructions pour mettre à jour vos projets Q#.

1. Pour commencer, vérifiez que vous disposez de la dernière version du [kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download). Exécutez la commande suivante à l’invite de commandes :

    ```dotnetcli
    dotnet --version
    ```

    Vérifiez que la sortie est `3.1.100` ou ultérieure. Si ce n’est pas le cas, installez la [dernière version](https://dotnet.microsoft.com/download) et revérifiez. Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement à la ligne de commande).

### <a name="update-q-projects-in-visual-studio"></a>Mettre à jour des projets Q# dans Visual Studio
 
1. Effectuez la mise à jour vers la dernière version de Visual Studio 2019. Pour obtenir des instructions, cliquez [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Ouvrez votre solution dans Visual Studio.
3. Dans le menu, sélectionnez **Générer** -> **Nettoyer la solution**.
4. Dans chacun de vos fichiers .csproj, mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).
    Autrement dit, modifiez les lignes du formulaire :

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. Dans chacun des fichiers .csproj, définissez le SDK avec `Microsoft.Quantum.Sdk`, comme indiqué dans la ligne ci-dessous. Notez que le numéro de version doit être le dernier disponible (pour savoir de quel numéro il s’agit, consultez les [notes de publication](https://docs.microsoft.com/quantum/relnotes/)).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Enregistrez et fermez tous les fichiers de votre solution.

7. Sélectionnez **Outils** -> **Ligne de commande** -> **Invite de commandes développeur**. Vous pouvez également utiliser la console du gestionnaire de package dans Visual Studio.

8. Pour chaque projet de la solution, exécutez la commande suivante pour **supprimer** ce package :

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Si vos projets utilisent d’autres packages Microsoft.Quantum ou Microsoft.Azure.Quantum (par exemple, Microsoft.Quantum.Numerics), exécutez la commande **add** pour mettre à jour la version utilisée.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Fermez l’invite de commandes et sélectionnez **Générer** -> **Générer la solution** (*ne sélectionnez pas* Regénérer la solution).

Vous pouvez maintenant passer directement à la [mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Mettre à jour des projets Q# dans Visual Studio Code

1. Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour.
2. Sélectionnez **Terminal** -> **Nouveau terminal**.
3. Suivez les instructions de mise à jour à l’aide de la ligne de commande (directement ci-dessous).

### <a name="update-q-projects-using-the-command-line"></a>Mettre à jour des projets Q# à l’aide de la ligne de commande

1. Accédez au dossier contenant votre fichier projet principal.

2. Exécutez la commande suivante :

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Déterminez la version actuelle du QDK. Pour la trouver, vous pouvez consulter les [notes de publication](https://docs.microsoft.com/quantum/relnotes/). Le format de la version est semblable à `0.11.2006.207`.

4. Dans chacun de vos fichiers `.csproj`, effectuez les étapes suivantes :

    - Mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque). Autrement dit, modifiez les lignes du formulaire :

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Remplacez la référence au SDK dans la définition du projet. Vérifiez que le numéro de version correspond à la valeur déterminée à l’**étape 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Supprimez la référence au package `Microsoft.Quantum.Development.Kit`, le cas échéant, qui est spécifiée dans l’entrée suivante :

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Mettez à jour la version de tous les packages Microsoft Quantum avec la dernière version du QDK (déterminée à l’**étape 3**). Les noms de ces packages respectent les formats suivants :

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Les références aux packages ont le format suivant :

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Enregistrez le fichier mis à jour.

    - Restaurez les dépendances du projet en effectuant les étapes suivantes :

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Retournez au dossier contenant votre projet principal et exécutez :

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Une fois vos projets Q# mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK.

## <a name="updating-the-qdk"></a>Mise à jour du QDK

Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.
Sélectionnez votre environnement de développement ci-dessous.

* [Python : mettre à jour l’extension IQ#](#update-iq-for-python)
* [Notebooks Jupyter : mettre à jour l’extension IQ#](#update-iq-for-jupyter-notebooks)
* [Visual Studio : mettre à jour l’extension QDK](#update-visual-studio-qdk-extension)
* [VS Code : mettre à jour l’extension QDK](#update-vs-code-qdk-extension)
* [Ligne de commande et C# : mettre à jour les modèles de projet](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Mettre à jour IQ# pour Python

1. Mettez à jour le noyau `iqsharp`. 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Vérifiez la version de `iqsharp`.

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Vous devez normalement voir la sortie suivante.

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, car vous devez utiliser la [dernière version disponible](xref:microsoft.quantum.relnotes).

3. Mettez à jour le package `qsharp`.

    ```
    pip install qsharp --upgrade
    ```

4. Vérifiez la version de `qsharp`.

    ```
    pip show qsharp
    ```

    Vous devez normalement voir la sortie suivante.

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs`.

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantiques existants.

### <a name="update-iq-for-jupyter-notebooks"></a>Mettre à jour IQ# pour les notebooks Jupyter

1. Mettez à jour le noyau `iqsharp`.

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Vérifiez la version de `iqsharp`.

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Le résultat doit ressembler à ce qui suit :

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, car vous devez utiliser la [dernière version disponible](xref:microsoft.quantum.relnotes).

3. Exécutez la commande suivante à partir d’une cellule dans votre notebook Jupyter :

    ```
    %workspace reload
    ```

4. Vous pouvez maintenant ouvrir un notebook Jupyter existant et l’exécuter avec le QDK mis à jour.

### <a name="update-visual-studio-qdk-extension"></a>Mettre à jour l’extension QDK Visual Studio

1. Mettez à jour l’extension Q# Visual Studio.

    - Visual Studio vous invite à accepter les mises à jour de l’[extension Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Acceptez la mise à jour.

    > [!NOTE]
    > Les modèles de projet sont mis à jour avec l’extension. Les modèles mis à jour s’appliquent uniquement aux projets que vous venez de créer. Le code pour vos projets existants n’est pas mis à jour quand l’extension est mise à jour.

### <a name="update-vs-code-qdk-extension"></a>Mettre à jour l’extension QDK VS Code

1. Mettez à jour l’extension VS Code Quantum.

    - Redémarrez VS Code.
    - Accédez à l’onglet **Extensions**.
    - Sélectionnez l’extension **Kit de développement Microsoft Quantum pour Visual Studio Code**.
    - Rechargez l’extension.

2. Mettez à jour les modèles de projet Quantum :

   - Accédez à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q# : Installer des modèles de projet**
   - Après quelques secondes, vous devriez obtenir un message indiquant que les modèles de projet ont bien été installés.

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, utilisation de l’outil en ligne de commande `dotnet`

1. Mettez à jour les modèles de projet Quantum pour .NET.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
