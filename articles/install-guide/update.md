---
title: Mettre à jour le kit de développement quantique (QDK)
description: 'Décrit comment mettre à jour vos projets Q # et le Microsoft Quantum Development Kit à la version actuelle.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327564"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a6543-103">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a6543-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a6543-104">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="a6543-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="a6543-105">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="a6543-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="a6543-106">Si vous installez pour la première fois, consultez le [Guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a6543-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="a6543-107">Nous vous recommandons de rester à jour avec la dernière version de QDK.</span><span class="sxs-lookup"><span data-stu-id="a6543-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="a6543-108">Suivez ce guide de mise à jour pour effectuer une mise à niveau vers la version la plus récente de QDK.</span><span class="sxs-lookup"><span data-stu-id="a6543-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="a6543-109">Le processus se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="a6543-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="a6543-110">Mise à jour de vos fichiers et projets Q # existants afin d’aligner votre code avec toute syntaxe mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a6543-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="a6543-111">Mise à jour du QDK lui-même pour l’environnement de développement choisi.</span><span class="sxs-lookup"><span data-stu-id="a6543-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="a6543-112">Mise à jour des projets Q #</span><span class="sxs-lookup"><span data-stu-id="a6543-112">Updating Q# Projects</span></span> 

<span data-ttu-id="a6543-113">Que vous utilisiez C# ou python pour héberger des opérations Q #, suivez ces instructions pour mettre à jour vos projets Q #.</span><span class="sxs-lookup"><span data-stu-id="a6543-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="a6543-114">Tout d’abord, vérifiez que vous disposez de la dernière version de la [kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="a6543-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="a6543-115">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="a6543-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="a6543-116">Vérifiez que la sortie est `3.1.100` ou supérieure.</span><span class="sxs-lookup"><span data-stu-id="a6543-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="a6543-117">Si ce n’est pas le cas, installez la [version la plus récente](https://dotnet.microsoft.com/download) et vérifiez à nouveau.</span><span class="sxs-lookup"><span data-stu-id="a6543-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="a6543-118">Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="a6543-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="a6543-119">Mettre à jour les projets Q # dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6543-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="a6543-120">Pour obtenir des instructions, [reportez](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) -vous à la version la plus récente de Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="a6543-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="a6543-121">Ouvrez votre solution dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a6543-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="a6543-122">Dans le menu, sélectionnez **générer**une  ->  **solution propre**.</span><span class="sxs-lookup"><span data-stu-id="a6543-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="a6543-123">Dans chacun de vos fichiers. csproj, mettez à jour la version cible de .NET Framework vers `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="a6543-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="a6543-124">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="a6543-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="a6543-125">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="a6543-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="a6543-126">Dans chacun des fichiers. csproj, définissez le kit de développement logiciel (SDK) sur `Microsoft.Quantum.Sdk` , comme indiqué dans la ligne ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a6543-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="a6543-127">Notez que le numéro de version doit être le dernier disponible et que vous pouvez le déterminer en consultant les [notes de publication](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="a6543-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="a6543-128">Enregistrez et fermez tous les fichiers de votre solution.</span><span class="sxs-lookup"><span data-stu-id="a6543-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="a6543-129">Sélectionnez **Outils**  ->  **ligne de commande**  ->  **invite de commandes développeur**.</span><span class="sxs-lookup"><span data-stu-id="a6543-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="a6543-130">Vous pouvez également utiliser la console de gestion des packages dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a6543-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="a6543-131">Pour chaque projet de la solution, exécutez la commande suivante pour **supprimer** ce package :</span><span class="sxs-lookup"><span data-stu-id="a6543-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="a6543-132">Si vos projets utilisent d’autres packages Microsoft. Quantum ou Microsoft. Azure. Quantum (par exemple, Microsoft. Quantum. Numerics), exécutez la commande **Add** pour ceux-ci afin de mettre à jour la version utilisée.</span><span class="sxs-lookup"><span data-stu-id="a6543-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="a6543-133">Fermez l’invite de commandes et sélectionnez **générer**  ->  **générer la solution** (ne sélectionnez *pas* régénérer la solution).</span><span class="sxs-lookup"><span data-stu-id="a6543-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="a6543-134">Vous pouvez maintenant passer directement à [la mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="a6543-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="a6543-135">Mettre à jour les projets Q # dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a6543-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="a6543-136">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="a6543-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="a6543-137">Sélectionnez **Terminal**  ->  **nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="a6543-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="a6543-138">Suivez les instructions relatives à la mise à jour à l’aide de la ligne de commande (directement ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="a6543-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="a6543-139">Mettre à jour les projets Q # à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="a6543-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="a6543-140">Accédez au dossier contenant votre fichier projet principal.</span><span class="sxs-lookup"><span data-stu-id="a6543-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="a6543-141">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a6543-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="a6543-142">Déterminez la version actuelle de QDK.</span><span class="sxs-lookup"><span data-stu-id="a6543-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="a6543-143">Pour le trouver, vous pouvez consulter les [notes de publication](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="a6543-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="a6543-144">Le format de la version est semblable à celui de `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="a6543-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="a6543-145">Dans chacun de vos `.csproj` fichiers, suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a6543-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="a6543-146">Mettez à jour la version cible de .NET Framework vers `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="a6543-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="a6543-147">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="a6543-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="a6543-148">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="a6543-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="a6543-149">Remplacez la référence au kit de développement logiciel (SDK) dans la définition du projet.</span><span class="sxs-lookup"><span data-stu-id="a6543-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="a6543-150">Assurez-vous que le numéro de version correspond à la valeur déterminée à l' **étape 3**.</span><span class="sxs-lookup"><span data-stu-id="a6543-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="a6543-151">Supprimez la référence au package `Microsoft.Quantum.Development.Kit` , le cas échéant, qui sera spécifiée dans l’entrée suivante :</span><span class="sxs-lookup"><span data-stu-id="a6543-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="a6543-152">Mettez à jour la version de tous les packages Microsoft Quantum vers la dernière version de QDK (déterminée à l' **étape 3**).</span><span class="sxs-lookup"><span data-stu-id="a6543-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="a6543-153">Ces packages sont nommés avec les modèles suivants :</span><span class="sxs-lookup"><span data-stu-id="a6543-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="a6543-154">Les références aux packages ont le format suivant :</span><span class="sxs-lookup"><span data-stu-id="a6543-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="a6543-155">Enregistrez le fichier mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a6543-155">Save the updated file.</span></span>

    - <span data-ttu-id="a6543-156">Restaurez les dépendances du projet, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="a6543-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="a6543-157">Revenez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="a6543-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="a6543-158">Une fois vos projets Q # mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK lui-même.</span><span class="sxs-lookup"><span data-stu-id="a6543-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="a6543-159">Mise à jour de QDK</span><span class="sxs-lookup"><span data-stu-id="a6543-159">Updating the QDK</span></span>

<span data-ttu-id="a6543-160">Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.</span><span class="sxs-lookup"><span data-stu-id="a6543-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="a6543-161">Sélectionnez votre environnement de développement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a6543-161">Select your development environment below.</span></span>

* [<span data-ttu-id="a6543-162">Python : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="a6543-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="a6543-163">Blocs-notes Jupyter : mettre à jour l’extension IQ #</span><span class="sxs-lookup"><span data-stu-id="a6543-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="a6543-164">Visual Studio : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="a6543-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="a6543-165">VS Code : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="a6543-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="a6543-166">Ligne de commande et C# : mettre à jour les modèles de projet</span><span class="sxs-lookup"><span data-stu-id="a6543-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="a6543-167">Mettre à jour IQ # pour Python</span><span class="sxs-lookup"><span data-stu-id="a6543-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="a6543-168">Mettre à jour le `iqsharp` noyau</span><span class="sxs-lookup"><span data-stu-id="a6543-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="a6543-169">Vérifier la `iqsharp` version</span><span class="sxs-lookup"><span data-stu-id="a6543-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a6543-170">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="a6543-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="a6543-171">Ne vous inquiétez pas si votre `iqsharp` version est plus élevée, elle doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="a6543-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="a6543-172">Mettre à jour le `qsharp` package</span><span class="sxs-lookup"><span data-stu-id="a6543-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="a6543-173">Vérifier la `qsharp` version</span><span class="sxs-lookup"><span data-stu-id="a6543-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="a6543-174">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="a6543-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="a6543-175">Exécutez la commande suivante à partir de l’emplacement de vos `.qs` fichiers</span><span class="sxs-lookup"><span data-stu-id="a6543-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="a6543-176">Vous pouvez maintenant utiliser la version mise à jour de QDK pour exécuter vos programmes quantum existants.</span><span class="sxs-lookup"><span data-stu-id="a6543-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="a6543-177">Mettre à jour IQ # pour les blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="a6543-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="a6543-178">Mettre à jour le `iqsharp` noyau</span><span class="sxs-lookup"><span data-stu-id="a6543-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="a6543-179">Vérifier la `iqsharp` version</span><span class="sxs-lookup"><span data-stu-id="a6543-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a6543-180">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a6543-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="a6543-181">Ne vous inquiétez pas si votre `iqsharp` version est plus élevée, elle doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="a6543-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="a6543-182">Exécutez la commande suivante à partir d’une cellule de votre Jupyter Notebook :</span><span class="sxs-lookup"><span data-stu-id="a6543-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="a6543-183">Vous pouvez maintenant ouvrir un bloc-notes Jupyter existant et l’exécuter avec le QDK mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a6543-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="a6543-184">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6543-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="a6543-185">Mettre à jour l’extension Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6543-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="a6543-186">Visual Studio vous invite à accepter les mises à jour de l' [extension Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="a6543-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="a6543-187">Accepter la mise à jour</span><span class="sxs-lookup"><span data-stu-id="a6543-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6543-188">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="a6543-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="a6543-189">Les modèles mis à jour s’appliquent uniquement aux projets nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="a6543-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="a6543-190">Le code de vos projets existants n’est pas mis à jour lorsque l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a6543-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="a6543-191">Mettre à jour VS Code extension QDK</span><span class="sxs-lookup"><span data-stu-id="a6543-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="a6543-192">Mettre à jour l’extension de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="a6543-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="a6543-193">Redémarrer VS Code</span><span class="sxs-lookup"><span data-stu-id="a6543-193">Restart VS Code</span></span>
    - <span data-ttu-id="a6543-194">Accédez à l’onglet **Extensions**</span><span class="sxs-lookup"><span data-stu-id="a6543-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="a6543-195">Sélectionner l' **Microsoft Quantum Development Kit pour l’extension de Visual Studio code**</span><span class="sxs-lookup"><span data-stu-id="a6543-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="a6543-196">Recharger l’extension</span><span class="sxs-lookup"><span data-stu-id="a6543-196">Reload the extension</span></span>

2. <span data-ttu-id="a6543-197">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="a6543-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="a6543-198">Accéder à **View**la  ->  **palette de commandes** de la vue</span><span class="sxs-lookup"><span data-stu-id="a6543-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="a6543-199">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="a6543-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="a6543-200">Après quelques secondes, vous devriez obtenir un message contextuel « les modèles de projet ont été installés avec succès »</span><span class="sxs-lookup"><span data-stu-id="a6543-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="a6543-201">C#, à l’aide de l' `dotnet` outil en ligne de commande</span><span class="sxs-lookup"><span data-stu-id="a6543-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="a6543-202">Mettre à jour les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="a6543-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
