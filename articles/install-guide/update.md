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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="4462f-102">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="4462f-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="4462f-103">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="4462f-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="4462f-104">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="4462f-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="4462f-105">Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="4462f-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="4462f-106">Mise à jour des projets Q #</span><span class="sxs-lookup"><span data-stu-id="4462f-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="4462f-107">Tout d’abord, installez la dernière version de la [kit SDK .NET Core 3,0](https://dotnet.microsoft.com/download) et exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="4462f-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="4462f-108">Vérifiez que la sortie est 3.0.100 ou supérieure, puis suivez les instructions ci-dessous en fonction de votre configuration.</span><span class="sxs-lookup"><span data-stu-id="4462f-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="4462f-109">Dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4462f-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="4462f-110">Mettez à jour vers la dernière version de Visual Studio 2019, voir [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pour obtenir des instructions</span><span class="sxs-lookup"><span data-stu-id="4462f-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="4462f-111">Ouvrez votre solution dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4462f-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="4462f-112">Dans le menu, sélectionnez Générer > nettoyer la solution</span><span class="sxs-lookup"><span data-stu-id="4462f-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="4462f-113">[Mettre à jour le Framework cible](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) dans chacun de vos fichiers. csproj vers netcoreapp 3.0 (ou netstandard 2.1 s’il s’agit d’un projet de bibliothèque)</span><span class="sxs-lookup"><span data-stu-id="4462f-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="4462f-114">Enregistrer et fermer tous les fichiers de votre solution</span><span class="sxs-lookup"><span data-stu-id="4462f-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="4462f-115">Sélectionnez Outils > > de ligne de commande Invite de commandes développeur</span><span class="sxs-lookup"><span data-stu-id="4462f-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="4462f-116">Pour chaque projet de la solution, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4462f-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="4462f-117">Si vos projets utilisent d’autres packages Microsoft. Quantum, exécutez la commande pour eux aussi.</span><span class="sxs-lookup"><span data-stu-id="4462f-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="4462f-118">Fermez l’invite de commandes et sélectionnez Générer > générer la solution (ne sélectionnez *pas* régénérer la solution, car la reconstruction échoue au départ)</span><span class="sxs-lookup"><span data-stu-id="4462f-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="4462f-119">Dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4462f-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="4462f-120">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour</span><span class="sxs-lookup"><span data-stu-id="4462f-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="4462f-121">Sélectionner terminal > nouveau terminal</span><span class="sxs-lookup"><span data-stu-id="4462f-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="4462f-122">Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="4462f-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="4462f-123">À l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="4462f-123">Using the command line</span></span>

1. <span data-ttu-id="4462f-124">Accédez au dossier contenant votre fichier projet</span><span class="sxs-lookup"><span data-stu-id="4462f-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="4462f-125">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4462f-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="4462f-126">[Mettre à jour le Framework cible](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) dans chacun de vos fichiers. csproj vers netcoreapp 3.0 (ou netstandard 2.1 s’il s’agit d’un projet de bibliothèque)</span><span class="sxs-lookup"><span data-stu-id="4462f-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="4462f-127">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4462f-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="4462f-128">Si votre projet utilise d’autres packages Microsoft. Quantum, exécutez la commande pour ceux-ci également.</span><span class="sxs-lookup"><span data-stu-id="4462f-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="4462f-129">Enregistrer et fermer tous les fichiers</span><span class="sxs-lookup"><span data-stu-id="4462f-129">Save and close all files</span></span>
6. <span data-ttu-id="4462f-130">Répétez 1-4 pour chaque dépendance de projet, puis revenez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="4462f-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="4462f-131">Mettre à jour IQ # pour Python</span><span class="sxs-lookup"><span data-stu-id="4462f-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="4462f-132">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4462f-133">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="4462f-134">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="4462f-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="4462f-135">Mettre à jour le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="4462f-136">Vérifier la version de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="4462f-137">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="4462f-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="4462f-138">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs`</span><span class="sxs-lookup"><span data-stu-id="4462f-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="4462f-139">Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.</span><span class="sxs-lookup"><span data-stu-id="4462f-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="4462f-140">Mettre à jour IQ # pour les blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="4462f-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="4462f-141">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4462f-142">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4462f-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="4462f-143">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="4462f-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="4462f-144">Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :</span><span class="sxs-lookup"><span data-stu-id="4462f-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="4462f-145">Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.</span><span class="sxs-lookup"><span data-stu-id="4462f-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="4462f-146">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4462f-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="4462f-147">Mettre à jour l’extension Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4462f-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4462f-148">Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4462f-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="4462f-149">Accepter la mise à jour</span><span class="sxs-lookup"><span data-stu-id="4462f-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="4462f-150">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="4462f-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="4462f-151">Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="4462f-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="4462f-152">Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="4462f-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="4462f-153">Mettre à jour VS Code extension QDK</span><span class="sxs-lookup"><span data-stu-id="4462f-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="4462f-154">Mettre à jour l’extension de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="4462f-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4462f-155">Redémarrer VS Code</span><span class="sxs-lookup"><span data-stu-id="4462f-155">Restart VS Code</span></span>
    - <span data-ttu-id="4462f-156">Accédez à l’onglet **Extensions**</span><span class="sxs-lookup"><span data-stu-id="4462f-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="4462f-157">Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**</span><span class="sxs-lookup"><span data-stu-id="4462f-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="4462f-158">Recharger l’extension</span><span class="sxs-lookup"><span data-stu-id="4462f-158">Reload the extension</span></span>

1. <span data-ttu-id="4462f-159">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="4462f-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="4462f-160">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="4462f-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4462f-161">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="4462f-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="4462f-162">C#, à l’aide de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="4462f-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="4462f-163">Mettre à jour les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="4462f-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="4462f-164">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="4462f-164">What's next?</span></span>

<span data-ttu-id="4462f-165">Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum.</span><span class="sxs-lookup"><span data-stu-id="4462f-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="4462f-166">Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="4462f-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
