---
title: En savoir plus sur la mise à jour des Microsoft Quantum Development Kit (QDK)
description: 'Décrit comment mettre à jour vos projets Q # et le Microsoft Quantum Development Kit à la version actuelle.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: bf6d6d3d80af485b555429f25b125bfea685bebf
ms.sourcegitcommit: c57c271ab73f75f165401651fad2b5bc143e9c8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82862205"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="efcec-103">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="efcec-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="efcec-104">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="efcec-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="efcec-105">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="efcec-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="efcec-106">Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="efcec-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="efcec-107">Nous vous recommandons de rester à jour avec la dernière version de QDK.</span><span class="sxs-lookup"><span data-stu-id="efcec-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="efcec-108">Suivez ce guide de mise à jour pour effectuer une mise à niveau vers la version la plus récente de QDK.</span><span class="sxs-lookup"><span data-stu-id="efcec-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="efcec-109">Le processus se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="efcec-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="efcec-110">mise à jour de vos projets et fichiers Q # existants afin d’aligner votre code avec toute syntaxe mise à jour</span><span class="sxs-lookup"><span data-stu-id="efcec-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="efcec-111">mise à jour du QDK lui-même pour l’environnement de développement choisi</span><span class="sxs-lookup"><span data-stu-id="efcec-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="efcec-112">Mise à jour des projets Q #</span><span class="sxs-lookup"><span data-stu-id="efcec-112">Updating Q# Projects</span></span> 

<span data-ttu-id="efcec-113">Que vous utilisiez C# ou python pour héberger des opérations Q #, suivez ces instructions pour mettre à jour vos projets Q #.</span><span class="sxs-lookup"><span data-stu-id="efcec-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="efcec-114">Tout d’abord, vérifiez que vous disposez de la dernière version de la [kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="efcec-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="efcec-115">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="efcec-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="efcec-116">Vérifiez que la sortie `3.1.100` est ou supérieure.</span><span class="sxs-lookup"><span data-stu-id="efcec-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="efcec-117">Si ce n’est pas le cas, installez la [version la plus récente](https://dotnet.microsoft.com/download) et vérifiez à nouveau.</span><span class="sxs-lookup"><span data-stu-id="efcec-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="efcec-118">Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="efcec-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="efcec-119">Mettre à jour les projets Q # dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efcec-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="efcec-120">Mettez à jour vers la dernière version de Visual Studio 2019, voir [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pour obtenir des instructions</span><span class="sxs-lookup"><span data-stu-id="efcec-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="efcec-121">Ouvrez votre solution dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efcec-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="efcec-122">Dans le menu, sélectionnez **générer** -> une**solution propre** .</span><span class="sxs-lookup"><span data-stu-id="efcec-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="efcec-123">Dans chacun de vos fichiers. csproj, mettez à jour la version `netcoreapp3.1` cible de `netstandard2.1` .NET Framework vers (ou s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="efcec-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="efcec-124">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="efcec-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="efcec-125">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="efcec-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="efcec-126">Enregistrer et fermer tous les fichiers de votre solution</span><span class="sxs-lookup"><span data-stu-id="efcec-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="efcec-127">Sélectionnez **Outils** -> **ligne** -> de commande**invite de commandes développeur**</span><span class="sxs-lookup"><span data-stu-id="efcec-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="efcec-128">Pour chaque projet de la solution, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="efcec-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="efcec-129">Si vos projets utilisent d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.</span><span class="sxs-lookup"><span data-stu-id="efcec-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="efcec-130">Fermez l’invite de commandes et sélectionnez **générer** -> **générer la solution** (ne sélectionnez *pas* régénérer la solution)</span><span class="sxs-lookup"><span data-stu-id="efcec-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="efcec-131">Vous pouvez maintenant passer directement à [la mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="efcec-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="efcec-132">Mettre à jour les projets Q # dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="efcec-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="efcec-133">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour</span><span class="sxs-lookup"><span data-stu-id="efcec-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="efcec-134">Sélectionner **Terminal** -> **nouveau terminal**</span><span class="sxs-lookup"><span data-stu-id="efcec-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="efcec-135">Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande (directement ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="efcec-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="efcec-136">Mettre à jour les projets Q # à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="efcec-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="efcec-137">Accédez au dossier contenant votre fichier projet</span><span class="sxs-lookup"><span data-stu-id="efcec-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="efcec-138">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="efcec-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="efcec-139">Dans chacun de vos fichiers. csproj, mettez à jour la version `netcoreapp3.1` cible de `netstandard2.1` .NET Framework vers (ou s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="efcec-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="efcec-140">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="efcec-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="efcec-141">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="efcec-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="efcec-142">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="efcec-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="efcec-143">Si votre projet utilise d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.</span><span class="sxs-lookup"><span data-stu-id="efcec-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="efcec-144">Enregistrez et fermez tous les fichiers.</span><span class="sxs-lookup"><span data-stu-id="efcec-144">Save and close all files.</span></span>
6. <span data-ttu-id="efcec-145">Répétez 1-4 pour chaque dépendance de projet, puis revenez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="efcec-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="efcec-146">Une fois vos projets Q # mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK lui-même.</span><span class="sxs-lookup"><span data-stu-id="efcec-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="efcec-147">Mise à jour de QDK</span><span class="sxs-lookup"><span data-stu-id="efcec-147">Updating the QDK</span></span>

<span data-ttu-id="efcec-148">Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.</span><span class="sxs-lookup"><span data-stu-id="efcec-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="efcec-149">Sélectionnez votre environnement de développement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="efcec-149">Select your development environment below.</span></span>

* [<span data-ttu-id="efcec-150">Python : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="efcec-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="efcec-151">Blocs-notes Jupyter : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="efcec-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="efcec-152">Visual Studio : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="efcec-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="efcec-153">VS Code : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="efcec-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="efcec-154">Ligne de commande et C# : mettre à jour les modèles de projet</span><span class="sxs-lookup"><span data-stu-id="efcec-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="efcec-155">Mettre à jour IQ # pour Python</span><span class="sxs-lookup"><span data-stu-id="efcec-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="efcec-156">Mettre à `iqsharp` jour le noyau</span><span class="sxs-lookup"><span data-stu-id="efcec-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="efcec-157">Vérifier la `iqsharp` version</span><span class="sxs-lookup"><span data-stu-id="efcec-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="efcec-158">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="efcec-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="efcec-159">Ne vous inquiétez `iqsharp` pas si votre version est plus élevée, elle doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="efcec-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="efcec-160">Mettre à `qsharp` jour le package</span><span class="sxs-lookup"><span data-stu-id="efcec-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="efcec-161">Vérifier la `qsharp` version</span><span class="sxs-lookup"><span data-stu-id="efcec-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="efcec-162">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="efcec-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="efcec-163">Exécutez la commande suivante à partir de l’emplacement `.qs` de vos fichiers</span><span class="sxs-lookup"><span data-stu-id="efcec-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="efcec-164">Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.</span><span class="sxs-lookup"><span data-stu-id="efcec-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="efcec-165">Mettre à jour IQ # pour les blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="efcec-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="efcec-166">Mettre à `iqsharp` jour le noyau</span><span class="sxs-lookup"><span data-stu-id="efcec-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="efcec-167">Vérifier la `iqsharp` version</span><span class="sxs-lookup"><span data-stu-id="efcec-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="efcec-168">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="efcec-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="efcec-169">Ne vous inquiétez `iqsharp` pas si votre version est plus élevée, elle doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="efcec-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="efcec-170">Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :</span><span class="sxs-lookup"><span data-stu-id="efcec-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="efcec-171">Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.</span><span class="sxs-lookup"><span data-stu-id="efcec-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="efcec-172">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efcec-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="efcec-173">Mettre à jour l’extension Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efcec-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="efcec-174">Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="efcec-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="efcec-175">Accepter la mise à jour</span><span class="sxs-lookup"><span data-stu-id="efcec-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="efcec-176">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="efcec-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="efcec-177">Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="efcec-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="efcec-178">Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="efcec-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="efcec-179">Mettre à jour VS Code extension QDK</span><span class="sxs-lookup"><span data-stu-id="efcec-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="efcec-180">Mettre à jour l’extension de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="efcec-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="efcec-181">Redémarrer VS Code</span><span class="sxs-lookup"><span data-stu-id="efcec-181">Restart VS Code</span></span>
    - <span data-ttu-id="efcec-182">Accédez à l’onglet **Extensions**</span><span class="sxs-lookup"><span data-stu-id="efcec-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="efcec-183">Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**</span><span class="sxs-lookup"><span data-stu-id="efcec-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="efcec-184">Recharger l’extension</span><span class="sxs-lookup"><span data-stu-id="efcec-184">Reload the extension</span></span>

2. <span data-ttu-id="efcec-185">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="efcec-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="efcec-186">Accéder à la**palette de commandes** de la **vue** -> </span><span class="sxs-lookup"><span data-stu-id="efcec-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="efcec-187">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="efcec-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="efcec-188">Après quelques secondes, vous devriez obtenir un message contextuel « les modèles de projet ont été installés avec succès »</span><span class="sxs-lookup"><span data-stu-id="efcec-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="efcec-189">C#, à l' `dotnet` aide de l’outil en ligne de commande</span><span class="sxs-lookup"><span data-stu-id="efcec-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="efcec-190">Mettre à jour les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="efcec-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="efcec-191">Quelle est l’étape suivante ?</span><span class="sxs-lookup"><span data-stu-id="efcec-191">What's next?</span></span>

<span data-ttu-id="efcec-192">Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum.</span><span class="sxs-lookup"><span data-stu-id="efcec-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="efcec-193">Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="efcec-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
