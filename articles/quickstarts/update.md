---
title: Mettre à jour le Quantum Development Kit (QDK)
description: Décrit comment mettre à jour vos projets Q# et le Microsoft Quantum Development Kit avec la version actuelle.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: quickstart
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1b5def3226bd073c878f8573aaddd757d733ec48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858056"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Mettre à jour le Microsoft Quantum Development Kit (QDK)

Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) avec la dernière version.

Cet article suppose que vous avez déjà installé le QDK. Si vous effectuez l’installation pour la première fois, consultez le [guide d’installation](xref:microsoft.quantum.install).

Nous vous recommandons d’utiliser la dernière version du QDK. Suivez ce guide de mise à jour pour effectuer la mise à niveau vers la dernière version du QDK. Le processus se compose de deux parties :
1. Mise à jour de vos fichiers et projets Q# existants afin d’aligner votre code avec toute syntaxe mise à jour.
2. Mise à jour du QDK à proprement dit pour l’environnement de développement choisi.

## <a name="updating-no-locq-projects"></a>Mise à jour des projets Q# 

Que vous utilisiez C# ou Python pour héberger des opérations Q#, suivez ces instructions pour mettre à jour vos projets Q#.

1. Pour commencer, vérifiez que vous disposez de la dernière version du [kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download). Exécutez la commande suivante à l’invite de commandes :

    ```dotnetcli
    dotnet --version
    ```

    Vérifiez que la sortie est `3.1.100` ou ultérieure. Si ce n’est pas le cas, installez la [dernière version](https://dotnet.microsoft.com/download) et revérifiez. Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement à l’invite de commandes).

### <a name="update-no-locq-projects-in-visual-studio"></a>Mettre à jour des projets Q# dans Visual Studio
 
1. Effectuez la mise à jour vers la dernière version de Visual Studio 2019. Pour obtenir des instructions, cliquez [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio).
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
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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


### <a name="update-no-locq-projects-in-visual-studio-code"></a>Mettre à jour des projets Q# dans Visual Studio Code

1. Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour.
2. Sélectionnez **Terminal** -> **Nouveau terminal**.
3. Suivez les instructions de mise à jour en utilisant l’invite de commandes (directement ci-dessous).

### <a name="update-no-locq-projects-using-the-command-prompt"></a>Mettre à jour des projets Q# en utilisant l’invite de commandes

1. Accédez au dossier contenant votre fichier projet principal.

2. Exécutez la commande suivante :

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Déterminez la version actuelle du QDK. Pour la trouver, vous pouvez consulter les [notes de publication](https://docs.microsoft.com/quantum/relnotes/). Le format de la version est semblable à `0.12.20072031`.

4. Dans chacun de vos fichiers `.csproj`, effectuez les étapes suivantes :

    - Mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque). Autrement dit, modifiez les lignes du formulaire :

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Remplacez la référence au SDK dans la définition du projet. Vérifiez que le numéro de version correspond à la valeur déterminée à l’**étape 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
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

* [Python : mettre à jour le package `qsharp`](#update-the-qsharp-python-package)
* [Notebooks Jupyter : mettre à jour le noyau IQ#](#update-the-iq-jupyter-kernel)
* [Visual Studio : mettre à jour l’extension QDK](#update-visual-studio-qdk-extension)
* [VS Code : mettre à jour l’extension QDK](#update-vs-code-qdk-extension)
* [Ligne de commande et C# : mettre à jour les modèles de projet](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>Mettre à jour le package Python `qsharp`

La procédure de mise à jour varie selon que vous avez procéder à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.

#### <a name="update-using-conda-recommended"></a>[Mise à jour à l’aide de conda (recommandé)](#tab/tabid-conda)

1. Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)](#tab/tabid-dotnetcli)

1. Mettez à jour le noyau `iqsharp`. 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifiez la version de `iqsharp`.

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Vous devez normalement voir la sortie suivante.

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Ce n’est pas un problème si votre version de `iqsharp` est ultérieure. Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).

1. Mettez à jour le package `qsharp` :

    ```
    pip install qsharp --upgrade
    ```

1. Vérifiez la version de `qsharp` :

    ```
    pip show qsharp
    ```

    Vous devez normalement voir la sortie suivante.

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Vous pouvez maintenant utiliser la version mise à jour du package Python `qsharp` pour exécuter vos programmes quantiques existants.

### <a name="update-the-ino-locq-jupyter-kernel"></a>Mettre à jour le noyau Jupyter IQ#

La procédure de mise à jour varie selon que vous avez procédé à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.

#### <a name="update-using-conda-recommended"></a>[Mise à jour à l’aide de conda (recommandé)](#tab/tabid-conda)

1. Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)](#tab/tabid-dotnetcli)

1. Mettez à jour le package `Microsoft.Quantum.IQSharp` :

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Vérifiez la version de `iqsharp` :

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Le résultat doit ressembler à ce qui suit :

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Ce n’est pas un problème si votre version de `iqsharp` est ultérieure. Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).

1. Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :

    ```
    %workspace reload
    ```

**_

Vous pouvez maintenant utiliser le noyau IQ# mis à jour pour exécuter vos notebooks Jupyter Q# existants.

### <a name="update-visual-studio-qdk-extension"></a>Mettre à jour l’extension QDK Visual Studio

1. Mettre à jour l’extension Visual Studio Q#

    - Visual Studio vous invite à accepter les mises à jour de l’[extension Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).
    - Acceptez la mise à jour.

    > [!NOTE]
    > Les modèles de projet sont mis à jour avec l’extension. Les modèles mis à jour s’appliquent uniquement aux projets que vous venez de créer. Le code pour vos projets existants n’est pas mis à jour quand l’extension est mise à jour.

### <a name="update-vs-code-qdk-extension"></a>Mettre à jour l’extension QDK VS Code

1. Mettez à jour l’extension VS Code Quantum.

    - Redémarrez VS Code.
    - Accéder à l’onglet _ *Extensions**
    - Sélectionnez l’extension **Kit de développement Microsoft Quantum pour Visual Studio Code**.
    - Rechargez l’extension.

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, utilisation de l’outil en ligne de commande `dotnet`

1. Mettez à jour les modèles de projet Quantum pour .NET.

    À partir de l’invite de commandes :

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Si vous envisagez d’utiliser les modèles de ligne de commande et que vous avez déjà installé l’extension VS Code QDK, vous pouvez aussi mettre à jour les modèles de projet à partir de l’extension elle-même :

   - [Mettre à jour l’extension QDK](#update-vs-code-qdk-extension)
   - Dans VS Code, accéder à **Affichage** -> **Palette de commandes**
   - Sélectionnez **Q# : Installer les modèles de projet de ligne de commande**
   - Après quelques secondes, vous devriez obtenir un message indiquant que les modèles de projet ont bien été installés.
