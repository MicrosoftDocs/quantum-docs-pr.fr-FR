---
title: En savoir plus sur la mise à jour des Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036306"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7b753-102">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7b753-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7b753-103">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="7b753-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="7b753-104">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="7b753-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="7b753-105">Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="7b753-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="7b753-106">Nous vous recommandons de rester à jour avec la dernière version de QDK.</span><span class="sxs-lookup"><span data-stu-id="7b753-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="7b753-107">Suivez ce guide de mise à jour pour effectuer une mise à niveau vers la version la plus récente de QDK.</span><span class="sxs-lookup"><span data-stu-id="7b753-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="7b753-108">Le processus se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="7b753-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="7b753-109">mise à jour de vos projets et fichiers Q # existants afin d’aligner votre code avec toute syntaxe mise à jour</span><span class="sxs-lookup"><span data-stu-id="7b753-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="7b753-110">mise à jour du QDK lui-même pour l’environnement de développement choisi</span><span class="sxs-lookup"><span data-stu-id="7b753-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="7b753-111">Mise à jour des projets Q #</span><span class="sxs-lookup"><span data-stu-id="7b753-111">Updating Q# Projects</span></span> 

<span data-ttu-id="7b753-112">Que vous utilisiez C# ou python pour héberger des opérations q #, suivez ces instructions pour mettre à jour vos projets q #.</span><span class="sxs-lookup"><span data-stu-id="7b753-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="7b753-113">Tout d’abord, vérifiez que vous disposez de la dernière version de la [kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="7b753-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="7b753-114">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="7b753-114">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="7b753-115">Vérifiez que la sortie est `3.1.100` ou supérieure.</span><span class="sxs-lookup"><span data-stu-id="7b753-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="7b753-116">Si ce n’est pas le cas, installez la [version la plus récente](https://dotnet.microsoft.com/download) et vérifiez à nouveau.</span><span class="sxs-lookup"><span data-stu-id="7b753-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="7b753-117">Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="7b753-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="7b753-118">Mettre à jour les projets Q # dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b753-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="7b753-119">Mettez à jour vers la dernière version de Visual Studio 2019, voir [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) pour obtenir des instructions</span><span class="sxs-lookup"><span data-stu-id="7b753-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="7b753-120">Ouvrez votre solution dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b753-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="7b753-121">Dans le menu, sélectionnez **générer** -> **nettoyer la solution**</span><span class="sxs-lookup"><span data-stu-id="7b753-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="7b753-122">Dans chacun de vos fichiers. csproj, mettez à jour la version cible de .NET Framework pour `netcoreapp3.0` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="7b753-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="7b753-123">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="7b753-123">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="7b753-124">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7b753-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="7b753-125">Enregistrer et fermer tous les fichiers de votre solution</span><span class="sxs-lookup"><span data-stu-id="7b753-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="7b753-126">Sélectionnez **outils** ->  -> de **ligne de commande** **invite de commandes développeur**</span><span class="sxs-lookup"><span data-stu-id="7b753-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="7b753-127">Pour chaque projet de la solution, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7b753-127">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="7b753-128">Si vos projets utilisent d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.</span><span class="sxs-lookup"><span data-stu-id="7b753-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="7b753-129">Fermez l’invite de commandes et sélectionnez **générer** -> **générer la solution** (ne sélectionnez *pas* régénérer la solution)</span><span class="sxs-lookup"><span data-stu-id="7b753-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="7b753-130">Vous pouvez maintenant passer directement à [la mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="7b753-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="7b753-131">Mettre à jour les projets Q # dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7b753-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="7b753-132">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour</span><span class="sxs-lookup"><span data-stu-id="7b753-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="7b753-133">Sélectionner **terminal** -> **nouveau terminal**</span><span class="sxs-lookup"><span data-stu-id="7b753-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="7b753-134">Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande (directement ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="7b753-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="7b753-135">Mettre à jour les projets Q # à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="7b753-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="7b753-136">Accédez au dossier contenant votre fichier projet</span><span class="sxs-lookup"><span data-stu-id="7b753-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="7b753-137">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7b753-137">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="7b753-138">Dans chacun de vos fichiers. csproj, mettez à jour la version cible de .NET Framework pour `netcoreapp3.0` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="7b753-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="7b753-139">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="7b753-139">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="7b753-140">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7b753-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="7b753-141">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7b753-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="7b753-142">Si votre projet utilise d’autres packages Microsoft. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande pour eux aussi.</span><span class="sxs-lookup"><span data-stu-id="7b753-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="7b753-143">Enregistrez et fermez tous les fichiers.</span><span class="sxs-lookup"><span data-stu-id="7b753-143">Save and close all files.</span></span>
6. <span data-ttu-id="7b753-144">Répétez 1-4 pour chaque dépendance de projet, puis revenez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="7b753-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="7b753-145">Une fois vos projets Q # mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK lui-même.</span><span class="sxs-lookup"><span data-stu-id="7b753-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="7b753-146">Mise à jour de QDK</span><span class="sxs-lookup"><span data-stu-id="7b753-146">Updating the QDK</span></span>

<span data-ttu-id="7b753-147">Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.</span><span class="sxs-lookup"><span data-stu-id="7b753-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="7b753-148">Sélectionnez votre environnement de développement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7b753-148">Select your development environment below.</span></span>

* [<span data-ttu-id="7b753-149">Python : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="7b753-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="7b753-150">Blocs-notes Jupyter : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="7b753-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="7b753-151">Visual Studio : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="7b753-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="7b753-152">VS Code : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="7b753-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="7b753-153">Ligne de commande et C#: mettre à jour les modèles de projet</span><span class="sxs-lookup"><span data-stu-id="7b753-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="7b753-154">Mettre à jour IQ # pour Python</span><span class="sxs-lookup"><span data-stu-id="7b753-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="7b753-155">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-155">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7b753-156">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-156">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7b753-157">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="7b753-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7b753-158">Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, elle doit correspondre à la version la [plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7b753-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7b753-159">Mettre à jour le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="7b753-160">Vérifier la version de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="7b753-161">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="7b753-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="7b753-162">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs`</span><span class="sxs-lookup"><span data-stu-id="7b753-162">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="7b753-163">Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.</span><span class="sxs-lookup"><span data-stu-id="7b753-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="7b753-164">Mettre à jour IQ # pour les blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="7b753-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="7b753-165">Mettre à jour le noyau `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-165">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7b753-166">Vérifier la version de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7b753-166">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7b753-167">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7b753-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7b753-168">Ne vous inquiétez pas si votre version de `iqsharp` est supérieure, elle doit correspondre à la version la [plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7b753-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7b753-169">Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :</span><span class="sxs-lookup"><span data-stu-id="7b753-169">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="7b753-170">Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.</span><span class="sxs-lookup"><span data-stu-id="7b753-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="7b753-171">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b753-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="7b753-172">Mettre à jour l’extension Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b753-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7b753-173">Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="7b753-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7b753-174">Accepter la mise à jour</span><span class="sxs-lookup"><span data-stu-id="7b753-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b753-175">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="7b753-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="7b753-176">Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="7b753-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="7b753-177">Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="7b753-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="7b753-178">Mettre à jour VS Code extension QDK</span><span class="sxs-lookup"><span data-stu-id="7b753-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="7b753-179">Mettre à jour l’extension de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="7b753-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7b753-180">Redémarrer VS Code</span><span class="sxs-lookup"><span data-stu-id="7b753-180">Restart VS Code</span></span>
    - <span data-ttu-id="7b753-181">Accédez à l’onglet **Extensions**</span><span class="sxs-lookup"><span data-stu-id="7b753-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="7b753-182">Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**</span><span class="sxs-lookup"><span data-stu-id="7b753-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="7b753-183">Recharger l’extension</span><span class="sxs-lookup"><span data-stu-id="7b753-183">Reload the extension</span></span>

2. <span data-ttu-id="7b753-184">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="7b753-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="7b753-185">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="7b753-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7b753-186">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="7b753-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="7b753-187">Après quelques secondes, vous devriez obtenir un message contextuel « les modèles de projet ont été installés avec succès »</span><span class="sxs-lookup"><span data-stu-id="7b753-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7b753-188">C#, à l’aide de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="7b753-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7b753-189">Mettre à jour les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="7b753-189">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="7b753-190">Quelle est l’étape suivante ?</span><span class="sxs-lookup"><span data-stu-id="7b753-190">What's next?</span></span>

<span data-ttu-id="7b753-191">Maintenant que vous avez mis à jour le kit de développement Quantum dans votre environnement préféré, vous pouvez continuer à développer et exécuter vos programmes Quantum.</span><span class="sxs-lookup"><span data-stu-id="7b753-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="7b753-192">Si vous n’avez pas encore écrit de programme, vous pouvez commencer à utiliser [votre premier programme Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="7b753-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
