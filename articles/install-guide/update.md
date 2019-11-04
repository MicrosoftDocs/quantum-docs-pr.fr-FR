---
title: En savoir plus sur la mise à jour des Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185849"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Mettre à jour le Microsoft Quantum Development Kit (QDK)

Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.

Cet article suppose que vous avez déjà installé le QDK. Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).

Les étapes de mise à jour dépendent de votre environnement de développement. Choisissez votre environnement dans les sections suivantes.

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.

## <a name="jupyter-notebooks"></a>Notebooks Jupyter

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.

## <a name="c-on-windows-using-visual-studio"></a>C#sur Windows, à l’aide de Visual Studio

1. Mettre à jour l’extension Q # Visual Studio

    - Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accepter la mise à jour

    > [!NOTE]
    > Les modèles de projet sont mis à jour avec l’extension. Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés. Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.

1. Mettre à jour les packages QDK

    - Ouvrir une application existante
    - Sélectionner les **dépendances** dans le Explorateur de solutions
    - Sélectionnez **gérer les packages NuGet**
    - Mettre à jour les packages **Microsoft. Quantum** vers la dernière version

1. Vous pouvez maintenant exécuter votre application avec la dernière version de QDK.

## <a name="c-using-vs-code"></a>C#, à l’aide de VS Code

1. Mettre à jour l’extension de VS Code Quantum

    - Redémarrer VS Code
    - Accédez à l’onglet **Extensions**
    - Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**
    - Recharger l’extension

1. Mettez à jour les modèles de projet Quantum :

   - Accéder à l' **affichage** -> à la **palette de commandes**
   - Sélectionnez **Q # : installer les modèles de projet**

1. Ouvrez une application existante dans VS Code

   - Modifier le fichier. csproj pour ajouter les nouvelles versions du package

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Si vous utilisez d’autres packages de `Microsoft.Quantum`, mettez-les à jour.

1. Vous pouvez maintenant exécuter votre application avec le QDK mis à jour

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, à l’aide de l’outil en ligne de commande `dotnet`

1. Mettre à jour les modèles de projet Quantum pour .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Mettre à jour et exécuter une application existante

    - Mettre à jour les versions de package QDK dans votre application

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Si votre application utilise d’autres packages de `Microsoft.Quantum`, mettez-les à jour.

    - Exécution de l’application

        ```bash
        dotnet run
        ```

    - Votre application s’exécute avec les nouvelles versions du package

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum. Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).
