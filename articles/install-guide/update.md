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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="609a1-102">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="609a1-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="609a1-103">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="609a1-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="609a1-104">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="609a1-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="609a1-105">Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="609a1-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="609a1-106">Les étapes de mise à jour dépendent de votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="609a1-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="609a1-107">Choisissez votre environnement dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="609a1-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="609a1-108">Python</span><span class="sxs-lookup"><span data-stu-id="609a1-108">Python</span></span>

1. <span data-ttu-id="609a1-109">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="609a1-110">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="609a1-111">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="609a1-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="609a1-112">Mettre à jour le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="609a1-113">Vérifier la version de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="609a1-114">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="609a1-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="609a1-115">Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.</span><span class="sxs-lookup"><span data-stu-id="609a1-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="609a1-116">Notebooks Jupyter</span><span class="sxs-lookup"><span data-stu-id="609a1-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="609a1-117">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="609a1-118">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="609a1-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="609a1-119">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="609a1-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="609a1-120">Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.</span><span class="sxs-lookup"><span data-stu-id="609a1-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="609a1-121">C#sur Windows, à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="609a1-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="609a1-122">Mettre à jour l’extension Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="609a1-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="609a1-123">Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="609a1-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="609a1-124">Accepter la mise à jour</span><span class="sxs-lookup"><span data-stu-id="609a1-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="609a1-125">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="609a1-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="609a1-126">Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="609a1-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="609a1-127">Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="609a1-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="609a1-128">Mettre à jour les packages QDK</span><span class="sxs-lookup"><span data-stu-id="609a1-128">Update the QDK packages</span></span>

    - <span data-ttu-id="609a1-129">Ouvrir une application existante</span><span class="sxs-lookup"><span data-stu-id="609a1-129">Open an existing application</span></span>
    - <span data-ttu-id="609a1-130">Sélectionner les **dépendances** dans le Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="609a1-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="609a1-131">Sélectionnez **gérer les packages NuGet**</span><span class="sxs-lookup"><span data-stu-id="609a1-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="609a1-132">Mettre à jour les packages **Microsoft. Quantum** vers la dernière version</span><span class="sxs-lookup"><span data-stu-id="609a1-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="609a1-133">Vous pouvez maintenant exécuter votre application avec la dernière version de QDK.</span><span class="sxs-lookup"><span data-stu-id="609a1-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="609a1-134">C#, à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="609a1-134">C#, using VS Code</span></span>

1. <span data-ttu-id="609a1-135">Mettre à jour l’extension de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="609a1-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="609a1-136">Redémarrer VS Code</span><span class="sxs-lookup"><span data-stu-id="609a1-136">Restart VS Code</span></span>
    - <span data-ttu-id="609a1-137">Accédez à l’onglet **Extensions**</span><span class="sxs-lookup"><span data-stu-id="609a1-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="609a1-138">Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**</span><span class="sxs-lookup"><span data-stu-id="609a1-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="609a1-139">Recharger l’extension</span><span class="sxs-lookup"><span data-stu-id="609a1-139">Reload the extension</span></span>

1. <span data-ttu-id="609a1-140">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="609a1-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="609a1-141">Accéder à l' **affichage** -> à la **palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="609a1-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="609a1-142">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="609a1-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="609a1-143">Ouvrez une application existante dans VS Code</span><span class="sxs-lookup"><span data-stu-id="609a1-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="609a1-144">Modifier le fichier. csproj pour ajouter les nouvelles versions du package</span><span class="sxs-lookup"><span data-stu-id="609a1-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="609a1-145">Si vous utilisez d’autres packages de `Microsoft.Quantum`, mettez-les à jour.</span><span class="sxs-lookup"><span data-stu-id="609a1-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="609a1-146">Vous pouvez maintenant exécuter votre application avec le QDK mis à jour</span><span class="sxs-lookup"><span data-stu-id="609a1-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="609a1-147">C#, à l’aide de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="609a1-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="609a1-148">Mettre à jour les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="609a1-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="609a1-149">Mettre à jour et exécuter une application existante</span><span class="sxs-lookup"><span data-stu-id="609a1-149">Update and run an existing application</span></span>

    - <span data-ttu-id="609a1-150">Mettre à jour les versions de package QDK dans votre application</span><span class="sxs-lookup"><span data-stu-id="609a1-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="609a1-151">Si votre application utilise d’autres packages de `Microsoft.Quantum`, mettez-les à jour.</span><span class="sxs-lookup"><span data-stu-id="609a1-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="609a1-152">Exécution de l’application</span><span class="sxs-lookup"><span data-stu-id="609a1-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="609a1-153">Votre application s’exécute avec les nouvelles versions du package</span><span class="sxs-lookup"><span data-stu-id="609a1-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="609a1-154">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="609a1-154">What's next?</span></span>

<span data-ttu-id="609a1-155">Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum.</span><span class="sxs-lookup"><span data-stu-id="609a1-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="609a1-156">Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="609a1-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
