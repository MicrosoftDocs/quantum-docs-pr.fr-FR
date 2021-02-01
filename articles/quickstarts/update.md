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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ce4bf-103">Mettre à jour le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="ce4bf-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ce4bf-104">Découvrez comment mettre à jour le Microsoft Quantum Development Kit (QDK) avec la dernière version.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="ce4bf-105">Cet article suppose que vous avez déjà installé le QDK.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="ce4bf-106">Si vous effectuez l’installation pour la première fois, consultez le [guide d’installation](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="ce4bf-107">Nous vous recommandons d’utiliser la dernière version du QDK.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="ce4bf-108">Suivez ce guide de mise à jour pour effectuer la mise à niveau vers la dernière version du QDK.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="ce4bf-109">Le processus se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="ce4bf-110">Mise à jour de vos fichiers et projets Q# existants afin d’aligner votre code avec toute syntaxe mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="ce4bf-111">Mise à jour du QDK à proprement dit pour l’environnement de développement choisi.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="ce4bf-112">Mise à jour des projets Q#</span><span class="sxs-lookup"><span data-stu-id="ce4bf-112">Updating Q# Projects</span></span> 

<span data-ttu-id="ce4bf-113">Que vous utilisiez C# ou Python pour héberger des opérations Q#, suivez ces instructions pour mettre à jour vos projets Q#.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="ce4bf-114">Pour commencer, vérifiez que vous disposez de la dernière version du [kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="ce4bf-115">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="ce4bf-116">Vérifiez que la sortie est `3.1.100` ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="ce4bf-117">Si ce n’est pas le cas, installez la [dernière version](https://dotnet.microsoft.com/download) et revérifiez.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="ce4bf-118">Suivez ensuite les instructions ci-dessous en fonction de votre configuration (Visual Studio, Visual Studio Code ou directement à l’invite de commandes).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="ce4bf-119">Mettre à jour des projets Q# dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce4bf-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="ce4bf-120">Effectuez la mise à jour vers la dernière version de Visual Studio 2019. Pour obtenir des instructions, cliquez [ici](https://docs.microsoft.com/visualstudio/install/update-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="ce4bf-121">Ouvrez votre solution dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="ce4bf-122">Dans le menu, sélectionnez **Générer** -> **Nettoyer la solution**.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="ce4bf-123">Dans chacun de vos fichiers .csproj, mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="ce4bf-124">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="ce4bf-125">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="ce4bf-126">Dans chacun des fichiers .csproj, définissez le SDK avec `Microsoft.Quantum.Sdk`, comme indiqué dans la ligne ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="ce4bf-127">Notez que le numéro de version doit être le dernier disponible (pour savoir de quel numéro il s’agit, consultez les [notes de publication](https://docs.microsoft.com/quantum/relnotes/)).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="ce4bf-128">Enregistrez et fermez tous les fichiers de votre solution.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="ce4bf-129">Sélectionnez **Outils** -> **Ligne de commande** -> **Invite de commandes développeur**.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="ce4bf-130">Vous pouvez également utiliser la console du gestionnaire de package dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="ce4bf-131">Pour chaque projet de la solution, exécutez la commande suivante pour **supprimer** ce package :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="ce4bf-132">Si vos projets utilisent d’autres packages Microsoft.Quantum ou Microsoft.Azure.Quantum (par exemple, Microsoft.Quantum.Numerics), exécutez la commande **add** pour mettre à jour la version utilisée.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="ce4bf-133">Fermez l’invite de commandes et sélectionnez **Générer** -> **Générer la solution** (*ne sélectionnez pas* Regénérer la solution).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="ce4bf-134">Vous pouvez maintenant passer directement à la [mise à jour de votre extension Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="ce4bf-135">Mettre à jour des projets Q# dans Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ce4bf-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="ce4bf-136">Dans Visual Studio Code, ouvrez le dossier contenant le projet à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="ce4bf-137">Sélectionnez **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="ce4bf-138">Suivez les instructions de mise à jour en utilisant l’invite de commandes (directement ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="ce4bf-139">Mettre à jour des projets Q# en utilisant l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="ce4bf-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="ce4bf-140">Accédez au dossier contenant votre fichier projet principal.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="ce4bf-141">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="ce4bf-142">Déterminez la version actuelle du QDK.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="ce4bf-143">Pour la trouver, vous pouvez consulter les [notes de publication](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="ce4bf-144">Le format de la version est semblable à `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="ce4bf-145">Dans chacun de vos fichiers `.csproj`, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="ce4bf-146">Mettez à jour le framework cible avec `netcoreapp3.1` (ou `netstandard2.1` s’il s’agit d’un projet de bibliothèque).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="ce4bf-147">Autrement dit, modifiez les lignes du formulaire :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="ce4bf-148">Vous trouverez plus d’informations sur la spécification des frameworks cibles [ici](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="ce4bf-149">Remplacez la référence au SDK dans la définition du projet.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="ce4bf-150">Vérifiez que le numéro de version correspond à la valeur déterminée à l’**étape 3**.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="ce4bf-151">Supprimez la référence au package `Microsoft.Quantum.Development.Kit`, le cas échéant, qui est spécifiée dans l’entrée suivante :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="ce4bf-152">Mettez à jour la version de tous les packages Microsoft Quantum avec la dernière version du QDK (déterminée à l’**étape 3**).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="ce4bf-153">Les noms de ces packages respectent les formats suivants :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="ce4bf-154">Les références aux packages ont le format suivant :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="ce4bf-155">Enregistrez le fichier mis à jour.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-155">Save the updated file.</span></span>

    - <span data-ttu-id="ce4bf-156">Restaurez les dépendances du projet en effectuant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="ce4bf-157">Retournez au dossier contenant votre projet principal et exécutez :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="ce4bf-158">Une fois vos projets Q# mis à jour, suivez les instructions ci-dessous pour mettre à jour le QDK.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="ce4bf-159">Mise à jour du QDK</span><span class="sxs-lookup"><span data-stu-id="ce4bf-159">Updating the QDK</span></span>

<span data-ttu-id="ce4bf-160">Le processus de mise à jour du QDK varie en fonction de votre environnement et de votre langage de développement.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="ce4bf-161">Sélectionnez votre environnement de développement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-161">Select your development environment below.</span></span>

* [<span data-ttu-id="ce4bf-162">Python : mettre à jour le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="ce4bf-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="ce4bf-163">Notebooks Jupyter : mettre à jour le noyau IQ#</span><span class="sxs-lookup"><span data-stu-id="ce4bf-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="ce4bf-164">Visual Studio : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="ce4bf-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="ce4bf-165">VS Code : mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="ce4bf-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="ce4bf-166">Ligne de commande et C# : mettre à jour les modèles de projet</span><span class="sxs-lookup"><span data-stu-id="ce4bf-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="ce4bf-167">Mettre à jour le package Python `qsharp`</span><span class="sxs-lookup"><span data-stu-id="ce4bf-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="ce4bf-168">La procédure de mise à jour varie selon que vous avez procéder à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="ce4bf-169">Mise à jour à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="ce4bf-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="ce4bf-170">Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="ce4bf-171">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="ce4bf-172">Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)</span><span class="sxs-lookup"><span data-stu-id="ce4bf-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="ce4bf-173">Mettez à jour le noyau `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ce4bf-174">Vérifiez la version de `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ce4bf-175">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="ce4bf-176">Ce n’est pas un problème si votre version de `iqsharp` est ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="ce4bf-177">Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="ce4bf-178">Mettez à jour le package `qsharp` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="ce4bf-179">Vérifiez la version de `qsharp` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="ce4bf-180">Vous devez normalement voir la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="ce4bf-181">Exécutez la commande suivante à partir de l’emplacement de vos fichiers `.qs` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="ce4bf-182">Vous pouvez maintenant utiliser la version mise à jour du package Python `qsharp` pour exécuter vos programmes quantiques existants.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="ce4bf-183">Mettre à jour le noyau Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="ce4bf-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="ce4bf-184">La procédure de mise à jour varie selon que vous avez procédé à une installation à l’aide de conda ou à l’aide de l’interface de commande .NET et de pip.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="ce4bf-185">Mise à jour à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="ce4bf-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="ce4bf-186">Activez l’environnement conda dans lequel vous avez installé le package `qsharp`, puis exécutez cette commande pour le mettre à jour :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="ce4bf-187">Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="ce4bf-188">Mise à jour à l’aide de l’interface CLI .NET et de pip (avancé)</span><span class="sxs-lookup"><span data-stu-id="ce4bf-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="ce4bf-189">Mettez à jour le package `Microsoft.Quantum.IQSharp` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ce4bf-190">Vérifiez la version de `iqsharp` :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ce4bf-191">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="ce4bf-192">Ce n’est pas un problème si votre version de `iqsharp` est ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="ce4bf-193">Celle-ci doit correspondre à la [version la plus récente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="ce4bf-194">Exécutez la commande suivante à partir d’une cellule dans chacun de vos notebooks Jupyter Q# existants :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

<span data-ttu-id="ce4bf-195">\*\*_</span><span class="sxs-lookup"><span data-stu-id="ce4bf-195">\*\*_</span></span>

<span data-ttu-id="ce4bf-196">Vous pouvez maintenant utiliser le noyau IQ# mis à jour pour exécuter vos notebooks Jupyter Q# existants.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-196">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="ce4bf-197">Mettre à jour l’extension QDK Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce4bf-197">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="ce4bf-198">Mettre à jour l’extension Visual Studio Q#</span><span class="sxs-lookup"><span data-stu-id="ce4bf-198">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ce4bf-199">Visual Studio vous invite à accepter les mises à jour de l’[extension Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="ce4bf-199">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ce4bf-200">Acceptez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-200">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce4bf-201">Les modèles de projet sont mis à jour avec l’extension.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-201">The project templates are updated with the extension.</span></span> <span data-ttu-id="ce4bf-202">Les modèles mis à jour s’appliquent uniquement aux projets que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-202">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="ce4bf-203">Le code pour vos projets existants n’est pas mis à jour quand l’extension est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-203">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="ce4bf-204">Mettre à jour l’extension QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="ce4bf-204">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="ce4bf-205">Mettez à jour l’extension VS Code Quantum.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-205">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ce4bf-206">Redémarrez VS Code.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-206">Restart VS Code</span></span>
    - <span data-ttu-id="ce4bf-207">Accéder à l’onglet _ *Extensions*\*</span><span class="sxs-lookup"><span data-stu-id="ce4bf-207">Navigate to the _ *Extensions*\* tab</span></span>
    - <span data-ttu-id="ce4bf-208">Sélectionnez l’extension **Kit de développement Microsoft Quantum pour Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-208">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="ce4bf-209">Rechargez l’extension.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-209">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ce4bf-210">C#, utilisation de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="ce4bf-210">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="ce4bf-211">Mettez à jour les modèles de projet Quantum pour .NET.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-211">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="ce4bf-212">À partir de l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-212">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="ce4bf-213">Si vous envisagez d’utiliser les modèles de ligne de commande et que vous avez déjà installé l’extension VS Code QDK, vous pouvez aussi mettre à jour les modèles de projet à partir de l’extension elle-même :</span><span class="sxs-lookup"><span data-stu-id="ce4bf-213">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="ce4bf-214">Mettre à jour l’extension QDK</span><span class="sxs-lookup"><span data-stu-id="ce4bf-214">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="ce4bf-215">Dans VS Code, accéder à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="ce4bf-215">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ce4bf-216">Sélectionnez **Q# : Installer les modèles de projet de ligne de commande**</span><span class="sxs-lookup"><span data-stu-id="ce4bf-216">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="ce4bf-217">Après quelques secondes, vous devriez obtenir un message indiquant que les modèles de projet ont bien été installés.</span><span class="sxs-lookup"><span data-stu-id="ce4bf-217">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
