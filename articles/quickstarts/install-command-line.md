---
title: Développer avec des applications Q# dans un IDE
description: Découvrez comment créer une application Q# qui s’exécute à partir de l’invite de commandes.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844314"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="569d9-103">Développer avec des applications Q# dans un IDE</span><span class="sxs-lookup"><span data-stu-id="569d9-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="569d9-104">Les programmes Q# peuvent s’exécuter seuls et sans pilote dans un langage hôte comme C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="569d9-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="569d9-105">Vous pouvez développer des applications Q# dans Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, ou avec n’importe quel éditeur/IDE et exécuter des applications à partir de la console .NET.</span><span class="sxs-lookup"><span data-stu-id="569d9-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="569d9-106">Prérequis pour tous les environnements</span><span class="sxs-lookup"><span data-stu-id="569d9-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="569d9-107">SDK .NET Core 3.1 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="569d9-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="569d9-108">Installation</span><span class="sxs-lookup"><span data-stu-id="569d9-108">Installation</span></span>

<span data-ttu-id="569d9-109">Même si vous pouvez générer des applications Q# dans n’importe quel IDE, nous vous recommandons d’utiliser l’IDE Visual Studio Code (VS Code) ou Visual Studio pour développer vos applications Q# localement.</span><span class="sxs-lookup"><span data-stu-id="569d9-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="569d9-110">Pour le développement dans le cloud via le navigateur web, nous vous recommandons Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="569d9-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="569d9-111">Lorsque vous développez dans ces environnements, vous pouvez tirer parti des nombreuses fonctionnalités de l’extension QDK, comme les avertissements, la coloration syntaxique, les modèles de projets, etc.</span><span class="sxs-lookup"><span data-stu-id="569d9-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="569d9-112">Pour configurer pour VS Code :</span><span class="sxs-lookup"><span data-stu-id="569d9-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="569d9-113">Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="569d9-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="569d9-114">Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="569d9-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="569d9-115">Pour configurer pour Visual Studio :</span><span class="sxs-lookup"><span data-stu-id="569d9-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="569d9-116">Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.</span><span class="sxs-lookup"><span data-stu-id="569d9-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="569d9-117">Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="569d9-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="569d9-118">Pour configurer pour un autre environnement :</span><span class="sxs-lookup"><span data-stu-id="569d9-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="569d9-119">À l’invite de commandes, entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="569d9-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="569d9-120">Pour configurer pour Visual Studio Codespaces :</span><span class="sxs-lookup"><span data-stu-id="569d9-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="569d9-121">Créez un [compte Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="569d9-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="569d9-122">Créez un environnement Codespaces.</span><span class="sxs-lookup"><span data-stu-id="569d9-122">Create a Codespaces environment.</span></span> <span data-ttu-id="569d9-123">Suivez le [guide de démarrage rapide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="569d9-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="569d9-124">Lorsque vous créez l’espace de code, nous vous recommandons d’entrer `microsoft/Quantum` dans le champ « Dépôt Git » pour charger les paramètres spécifiques au QDK.</span><span class="sxs-lookup"><span data-stu-id="569d9-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="569d9-125">Vous pouvez maintenant lancer votre nouvel environnement et commencer à développer dans le navigateur via l’[IDE cloud VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="569d9-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="569d9-126">Il est également possible d’utiliser votre installation locale de VS Code et d’utiliser Codespaces comme [environnement distant](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="569d9-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="569d9-127">Développer avec Q#</span><span class="sxs-lookup"><span data-stu-id="569d9-127">Develop with Q#</span></span>

<span data-ttu-id="569d9-128">Suivez les instructions sous l’onglet correspondant à votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="569d9-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="569d9-129">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="569d9-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="569d9-130">Pour créer un projet :</span><span class="sxs-lookup"><span data-stu-id="569d9-130">To create a new project:</span></span>

1. <span data-ttu-id="569d9-131">Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="569d9-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="569d9-132">Cliquez sur **Application console autonome**.</span><span class="sxs-lookup"><span data-stu-id="569d9-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="569d9-133">Accédez à l’emplacement d’enregistrement du projet.</span><span class="sxs-lookup"><span data-stu-id="569d9-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="569d9-134">Entrez le nom du projet et cliquez sur **Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="569d9-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="569d9-135">Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="569d9-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="569d9-136">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="569d9-136">Inspect the project.</span></span> <span data-ttu-id="569d9-137">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="569d9-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="569d9-138">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="569d9-138">To run the application:</span></span>

1. <span data-ttu-id="569d9-139">Cliquez sur **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="569d9-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="569d9-140">À l’invite du terminal, entrez `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="569d9-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="569d9-141">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="569d9-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="569d9-142">Les espaces de travail avec plusieurs dossiers racine ne sont pas actuellement pris en charge par l’extension VS Code Q#.</span><span class="sxs-lookup"><span data-stu-id="569d9-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="569d9-143">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="569d9-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="569d9-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="569d9-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="569d9-145">Vérifiez votre installation de Visual Studio en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="569d9-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="569d9-146">Pour créer une application Q# :</span><span class="sxs-lookup"><span data-stu-id="569d9-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="569d9-147">Ouvrez Visual Studio, puis cliquez sur **Fichier** -> **Nouveau** -> **Projet**.</span><span class="sxs-lookup"><span data-stu-id="569d9-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="569d9-148">Tapez `Q#` dans la zone de recherche, sélectionnez **Application Q#** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="569d9-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="569d9-149">Entrez un nom et un emplacement pour votre application, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="569d9-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="569d9-150">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="569d9-150">Inspect the project.</span></span> <span data-ttu-id="569d9-151">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="569d9-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="569d9-152">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="569d9-152">To run the application:</span></span>

1. <span data-ttu-id="569d9-153">Sélectionnez **Déboguer** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="569d9-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="569d9-154">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="569d9-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="569d9-155">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="569d9-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="569d9-156">Autres éditeurs avec l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="569d9-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="569d9-157">Vérifiez votre installation en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="569d9-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="569d9-158">Créez une application :</span><span class="sxs-lookup"><span data-stu-id="569d9-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="569d9-159">Accédez au répertoire de l’application :</span><span class="sxs-lookup"><span data-stu-id="569d9-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="569d9-160">Ce répertoire doit maintenant contenir un fichier `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="569d9-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="569d9-161">Vous pouvez modifier ce modèle avec un éditeur de texte et le remplacer par vos propres applications quantiques.</span><span class="sxs-lookup"><span data-stu-id="569d9-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="569d9-162">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="569d9-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="569d9-163">Le texte suivant doit s’afficher : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="569d9-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="569d9-164">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="569d9-164">Next steps</span></span>

<span data-ttu-id="569d9-165">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="569d9-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
