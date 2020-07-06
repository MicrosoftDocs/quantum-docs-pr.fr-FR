---
title: Mettre à jour le Quantum Development Kit (QDK)
description: Décrit comment mettre à jour vos projets Q# et le Microsoft Quantum Development Kit avec la version actuelle.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 457083ea4756d64375834e5a276c2d91031138fe
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885150"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="20c94-103">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="20c94-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="20c94-104">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) avec la dernière version.</span><span class="sxs-lookup"><span data-stu-id="20c94-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="20c94-105">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="20c94-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="20c94-106">Si vous effectuez l’installation pour la première fois, consultez le [guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="20c94-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="20c94-107">Nous vous recommandons d’utiliser la dernière version du QDK.</span><span class="sxs-lookup"><span data-stu-id="20c94-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="20c94-108">Suivez ce guide de mise à jour pour effectuer la mise à niveau vers la dernière version du QDK.</span><span class="sxs-lookup"><span data-stu-id="20c94-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="20c94-109">Le processus se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="20c94-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="20c94-110">Mise à jour de vos fichiers et projets Q# existants afin d’aligner votre code avec toute syntaxe mise à jour.</span><span class="sxs-lookup"><span data-stu-id="20c94-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="20c94-111">Mise à jour du QDK à proprement dit pour l’environnement de développement choisi.</span><span class="sxs-lookup"><span data-stu-id="20c94-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="20c94-112">Mise à jour des projets Q#</span><span class="sxs-lookup"><span data-stu-id="20c94-112">Updating Q# Projects</span></span> 

<span data-ttu-id="20c94-113">Que vous utilisiez C# ou Python pour héberger des opérations Q#, suivez ces instructions pour mettre à jour vos projets Q#.</span><span class="sxs-lookup"><span data-stu-id="20c94-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="20c94-114">Pour commencer, vérifiez que vous disposez de la dernière version du [kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="20c94-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="20c94-115">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="20c94-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="20c94-116">Vérifiez que la sortie est `3.1.100` ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="20c94-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="20c94-117">Si ce n’est pas le cas, installez la [dernière version](https://dotnet.microsoft.com/download) et revérifiez.</span><span class="sxs-lookup"><span data-stu-id="20c94-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="20c94-118">Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement à la ligne de commande).</span><span class="sxs-lookup"><span data-stu-id="20c94-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="20c94-119">Mettre à jour des projets Q# dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20c94-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="20c94-120">Effectuez la mise à jour vers la dernière version de Visual Studio 2019. Pour obtenir des instructions, cliquez [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="20c94-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="20c94-121">Ouvrez votre solution dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20c94-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="20c94-122">Dans le menu, sélectionnez **Générer** -> **Nettoyer la solution**.</span><span class="sxs-lookup"><span data-stu-id="20c94-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="20c94-123">Dans chacun de vos fichiers .csproj, mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="20c94-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="20c94-124">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="20c94-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="20c94-125">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="20c94-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="20c94-126">Dans chacun des fichiers .csproj, définissez le SDK avec `Microsoft.Quantum.Sdk`, comme indiqué dans la ligne ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="20c94-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="20c94-127">Notez que le numéro de version doit être le dernier disponible (pour savoir de quel numéro il s’agit, consultez les [notes de publication](https://docs.microsoft.com/quantum/relnotes/)).</span><span class="sxs-lookup"><span data-stu-id="20c94-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="20c94-128">Enregistrez et fermez tous les fichiers de votre solution.</span><span class="sxs-lookup"><span data-stu-id="20c94-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="20c94-129">Sélectionnez **Outils** -> **Ligne de commande** -> **Invite de commandes développeur**.</span><span class="sxs-lookup"><span data-stu-id="20c94-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="20c94-130">Vous pouvez également utiliser la console du gestionnaire de package dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20c94-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="20c94-131">Pour chaque projet de la solution, exécutez la commande suivante pour **supprimer** ce package :</span><span class="sxs-lookup"><span data-stu-id="20c94-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="20c94-132">Si vos projets utilisent d’autres packages Microsoft.Quantum ou Microsoft.Azure.Quantum (par exemple, Microsoft.Quantum.Numerics), exécutez la commande **add** pour mettre à jour la version utilisée.</span><span class="sxs-lookup"><span data-stu-id="20c94-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="20c94-133">Fermez l’invite de commandes et sélectionnez **Générer** -> **Générer la solution** (*ne sélectionnez pas* Regénérer la solution).</span><span class="sxs-lookup"><span data-stu-id="20c94-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="20c94-134">Vous pouvez maintenant passer directement à la [mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="20c94-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="20c94-135">Mettre à jour des projets Q# dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="20c94-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="20c94-136">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="20c94-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="20c94-137">Sélectionnez **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="20c94-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="20c94-138">Suivez les instructions de mise à jour à l’aide de la ligne de commande (directement ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="20c94-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="20c94-139">Mettre à jour des projets Q# à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="20c94-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="20c94-140">Accédez au dossier contenant votre fichier projet principal.</span><span class="sxs-lookup"><span data-stu-id="20c94-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="20c94-141">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="20c94-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="20c94-142">Déterminez la version actuelle du QDK.</span><span class="sxs-lookup"><span data-stu-id="20c94-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="20c94-143">Pour la trouver, vous pouvez consulter les [notes de publication](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="20c94-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="20c94-144">Le format de la version est semblable à `0.11.2006.207`.</span><span class="sxs-lookup"><span data-stu-id="20c94-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="20c94-145">Dans chacun de vos fichiers `.csproj`, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="20c94-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="20c94-146">Mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="20c94-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="20c94-147">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="20c94-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="20c94-148">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="20c94-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="20c94-149">Remplacez la référence au SDK dans la définition du projet.</span><span class="sxs-lookup"><span data-stu-id="20c94-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="20c94-150">Vérifiez que le numéro de version correspond à la valeur déterminée à l’**étape 3**.</span><span class="sxs-lookup"><span data-stu-id="20c94-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="20c94-151">Supprimez la référence au package `Microsoft.Quantum.Development.Kit`, le cas échéant, qui est spécifiée dans l’entrée suivante :</span><span class="sxs-lookup"><span data-stu-id="20c94-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="20c94-152">Mettez à jour la version de tous les packages Microsoft Quantum avec la dernière version du QDK (déterminée à l’**étape 3**).</span><span class="sxs-lookup"><span data-stu-id="20c94-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="20c94-153">Les noms de ces packages respectent les formats suivants :</span><span class="sxs-lookup"><span data-stu-id="20c94-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="20c94-154">Les références aux packages ont le format suivant :</span><span class="sxs-lookup"><span data-stu-id="20c94-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="20c94-155">Enregistrez le fichier mis à jour.</span><span class="sxs-lookup"><span data-stu-id="20c94-155">Save the updated file.</span></span>

    - <span data-ttu-id="20c94-156">Restaurez les dépendances du projet en effectuant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="20c94-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="20c94-157">Retournez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="20c94-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="20c94-158">Une fois vos projets Q# mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK.</span><span class="sxs-lookup"><span data-stu-id="20c94-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="20c94-159">Mise à jour du QDK</span><span class="sxs-lookup"><span data-stu-id="20c94-159">Updating the QDK</span></span>

<span data-ttu-id="20c94-160">Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.</span><span class="sxs-lookup"><span data-stu-id="20c94-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="20c94-161">Sélectionnez votre environnement de développement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="20c94-161">Select your development environment below.</span></span>

* [<span data-ttu-id="20c94-162">Python : mettre à jour le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="20c94-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="20c94-163">Notebooks Jupyter : mettre à jour le noyau IQ#</span><span class="sxs-lookup"><span data-stu-id="20c94-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="20c94-164">Visual Studio : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="20c94-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="20c94-165">VS Code : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="20c94-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="20c94-166">Ligne de commande et C# : mettre à jour les modèles de projet</span><span class="sxs-lookup"><span data-stu-id="20c94-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="20c94-167">Mettre à jour le package Python `qsharp`</span><span class="sxs-lookup"><span data-stu-id="20c94-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="20c94-168">La procédure de mise à jour varie selon que vous avez procéder à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.</span><span class="sxs-lookup"><span data-stu-id="20c94-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="20c94-169">Mise à jour à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="20c94-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="20c94-170">Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :</span><span class="sxs-lookup"><span data-stu-id="20c94-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="20c94-171">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :</span><span class="sxs-lookup"><span data-stu-id="20c94-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="20c94-172">Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)</span><span class="sxs-lookup"><span data-stu-id="20c94-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="20c94-173">Mettez à jour le noyau `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="20c94-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="20c94-174">Vérifiez la version de `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="20c94-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="20c94-175">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="20c94-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="20c94-176">Ce n’est pas un problème si votre version de `iqsharp` est ultérieure.</span><span class="sxs-lookup"><span data-stu-id="20c94-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="20c94-177">Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="20c94-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="20c94-178">Mettez à jour le package `qsharp` :</span><span class="sxs-lookup"><span data-stu-id="20c94-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="20c94-179">Vérifiez la version de `qsharp` :</span><span class="sxs-lookup"><span data-stu-id="20c94-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="20c94-180">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="20c94-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.20070124
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="20c94-181">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :</span><span class="sxs-lookup"><span data-stu-id="20c94-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="20c94-182">Vous pouvez maintenant utiliser la version mise à jour du package Python `qsharp` pour exécuter vos programmes quantiques existants.</span><span class="sxs-lookup"><span data-stu-id="20c94-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-iq-jupyter-kernel"></a><span data-ttu-id="20c94-183">Mettre à jour le noyau Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="20c94-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="20c94-184">La procédure de mise à jour varie selon que vous avez procédé à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.</span><span class="sxs-lookup"><span data-stu-id="20c94-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="20c94-185">Mise à jour à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="20c94-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="20c94-186">Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :</span><span class="sxs-lookup"><span data-stu-id="20c94-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="20c94-187">Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :</span><span class="sxs-lookup"><span data-stu-id="20c94-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="20c94-188">Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)</span><span class="sxs-lookup"><span data-stu-id="20c94-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="20c94-189">Mettez à jour le package `Microsoft.Quantum.IQSharp` :</span><span class="sxs-lookup"><span data-stu-id="20c94-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="20c94-190">Vérifiez la version de `iqsharp` :</span><span class="sxs-lookup"><span data-stu-id="20c94-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="20c94-191">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="20c94-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="20c94-192">Ce n’est pas un problème si votre version de `iqsharp` est ultérieure.</span><span class="sxs-lookup"><span data-stu-id="20c94-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="20c94-193">Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="20c94-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="20c94-194">Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :</span><span class="sxs-lookup"><span data-stu-id="20c94-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="20c94-195">Vous pouvez maintenant utiliser le noyau IQ# mis à jour pour exécuter vos notebooks Jupyter Q# existants.</span><span class="sxs-lookup"><span data-stu-id="20c94-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="20c94-196">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20c94-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="20c94-197">Mettez à jour l’extension Q# Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20c94-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="20c94-198">Visual Studio vous invite à accepter les mises à jour de l’[extension Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="20c94-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="20c94-199">Acceptez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="20c94-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="20c94-200">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="20c94-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="20c94-201">Les modèles mis à jour s’appliquent uniquement aux projets que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="20c94-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="20c94-202">Le code pour vos projets existants n’est pas mis à jour quand l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="20c94-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="20c94-203">Mettre à jour l’extension QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="20c94-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="20c94-204">Mettez à jour l’extension VS Code Quantum.</span><span class="sxs-lookup"><span data-stu-id="20c94-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="20c94-205">Redémarrez VS Code.</span><span class="sxs-lookup"><span data-stu-id="20c94-205">Restart VS Code</span></span>
    - <span data-ttu-id="20c94-206">Accédez à l’onglet **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="20c94-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="20c94-207">Sélectionnez l’extension **Kit de développement Microsoft Quantum pour Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="20c94-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="20c94-208">Rechargez l’extension.</span><span class="sxs-lookup"><span data-stu-id="20c94-208">Reload the extension</span></span>

2. <span data-ttu-id="20c94-209">Mettez à jour les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="20c94-209">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="20c94-210">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="20c94-210">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="20c94-211">Sélectionnez **Q# : Installer des modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="20c94-211">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="20c94-212">Après quelques secondes, vous devriez obtenir un message indiquant que les modèles de projet ont bien été installés.</span><span class="sxs-lookup"><span data-stu-id="20c94-212">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="20c94-213">C#, utilisation de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="20c94-213">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="20c94-214">Mettez à jour les modèles de projet Quantum pour .NET.</span><span class="sxs-lookup"><span data-stu-id="20c94-214">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
