---
title: Développer avec des applications Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a630b2307f5d95321fb26f480d7a441ddba846fc
ms.sourcegitcommit: d6ac6f4345be0dd68f1bcd944f44b08e7a3cf346
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358256"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="4c278-102">Développer avec des applications Q#</span><span class="sxs-lookup"><span data-stu-id="4c278-102">Develop with Q# applications</span></span>

<span data-ttu-id="4c278-103">Les programmes Q# peuvent être exécutés seuls et sans pilote dans un langage hôte comme C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="4c278-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c278-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4c278-104">Prerequisites</span></span>

- [<span data-ttu-id="4c278-105">SDK .NET Core 3.1 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="4c278-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="4c278-106">Installation</span><span class="sxs-lookup"><span data-stu-id="4c278-106">Installation</span></span>

<span data-ttu-id="4c278-107">Même si vous pouvez générer des applications Q# dans n’importe quel IDE, nous vous recommandons d’utiliser l’IDE Visual Studio Code (VS Code) ou Visual Studio pour développer vos applications Q# localement.</span><span class="sxs-lookup"><span data-stu-id="4c278-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="4c278-108">Pour le développement dans le cloud via le navigateur web, nous vous recommandons Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="4c278-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="4c278-109">Lorsque vous développez dans ces environnements, vous pouvez tirer parti des nombreuses fonctionnalités de l’extension QDK, comme les avertissements, la coloration syntaxique, les modèles de projets, etc.</span><span class="sxs-lookup"><span data-stu-id="4c278-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="4c278-110">Pour configurer VS Code :</span><span class="sxs-lookup"><span data-stu-id="4c278-110">To configure VS Code:</span></span>

1. <span data-ttu-id="4c278-111">Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="4c278-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="4c278-112">Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="4c278-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="4c278-113">Pour configurer Visual Studio :</span><span class="sxs-lookup"><span data-stu-id="4c278-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="4c278-114">Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.</span><span class="sxs-lookup"><span data-stu-id="4c278-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="4c278-115">Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="4c278-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="4c278-116">Pour configurer Visual Studio Codespaces :</span><span class="sxs-lookup"><span data-stu-id="4c278-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="4c278-117">Créez un [compte Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="4c278-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="4c278-118">Créez un environnement Codespaces.</span><span class="sxs-lookup"><span data-stu-id="4c278-118">Create a Codespaces environment.</span></span> <span data-ttu-id="4c278-119">Suivez le [guide de démarrage rapide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="4c278-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="4c278-120">Lorsque vous créez l’espace de code, nous vous recommandons d’entrer `microsoft/Quantum` dans le champ « Dépôt Git » pour charger les paramètres spécifiques au QDK.</span><span class="sxs-lookup"><span data-stu-id="4c278-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="4c278-121">Vous pouvez maintenant lancer votre nouvel environnement et commencer à développer dans le navigateur via l’[IDE cloud VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="4c278-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="4c278-122">Il est également possible d’utiliser votre installation locale de VS Code et d’utiliser Codespaces comme [environnement distant](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="4c278-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="4c278-123">Si vous souhaitez installer le QDK pour un autre environnement, entrez ceci à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="4c278-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="4c278-124">Développer avec Q#</span><span class="sxs-lookup"><span data-stu-id="4c278-124">Develop with Q#</span></span>

<span data-ttu-id="4c278-125">Suivez les instructions situées sous l’onglet correspondant à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="4c278-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="4c278-126">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4c278-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4c278-127">Pour créer un projet :</span><span class="sxs-lookup"><span data-stu-id="4c278-127">To create a new project:</span></span>

1. <span data-ttu-id="4c278-128">Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="4c278-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="4c278-129">Cliquez sur **Application console autonome**.</span><span class="sxs-lookup"><span data-stu-id="4c278-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="4c278-130">Accédez à l’emplacement où vous souhaitez enregistrer le projet, puis cliquez sur **Créer le projet**.</span><span class="sxs-lookup"><span data-stu-id="4c278-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="4c278-131">Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="4c278-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="4c278-132">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="4c278-132">Inspect the project.</span></span> <span data-ttu-id="4c278-133">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="4c278-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="4c278-134">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="4c278-134">To run the application:</span></span>
1. <span data-ttu-id="4c278-135">Cliquez sur **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="4c278-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="4c278-136">À l’invite du terminal, entrez `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4c278-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="4c278-137">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4c278-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="4c278-138">Les espaces de travail avec plusieurs dossiers racine ne sont pas actuellement pris en charge par l’extension VS Code Q#.</span><span class="sxs-lookup"><span data-stu-id="4c278-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="4c278-139">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="4c278-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="4c278-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4c278-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="4c278-141">Vérifiez votre installation de Visual Studio en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="4c278-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="4c278-142">Pour créer une application Q# :</span><span class="sxs-lookup"><span data-stu-id="4c278-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="4c278-143">Ouvrez Visual Studio, puis cliquez sur **Fichier** -> **Nouveau** -> **Projet**.</span><span class="sxs-lookup"><span data-stu-id="4c278-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="4c278-144">Tapez `Q#` dans la zone de recherche, sélectionnez **Application Q#** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4c278-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="4c278-145">Entrez un nom et un emplacement pour votre application, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="4c278-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="4c278-146">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="4c278-146">Inspect the project.</span></span> <span data-ttu-id="4c278-147">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="4c278-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="4c278-148">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="4c278-148">To run the application:</span></span>
1. <span data-ttu-id="4c278-149">Sélectionnez **Déboguer** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="4c278-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="4c278-150">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="4c278-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="4c278-151">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="4c278-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="4c278-152">Autres éditeurs avec l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="4c278-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="4c278-153">Vérifiez votre installation en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="4c278-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="4c278-154">Installez les modèles de projet.</span><span class="sxs-lookup"><span data-stu-id="4c278-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="4c278-155">Créez une application :</span><span class="sxs-lookup"><span data-stu-id="4c278-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="4c278-156">Accédez au répertoire de l’application :</span><span class="sxs-lookup"><span data-stu-id="4c278-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="4c278-157">Ce répertoire doit maintenant contenir un fichier `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="4c278-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="4c278-158">Vous pouvez modifier ce modèle avec un éditeur de texte et le remplacer par vos propres applications quantiques.</span><span class="sxs-lookup"><span data-stu-id="4c278-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="4c278-159">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="4c278-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="4c278-160">Le texte suivant doit s’afficher : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4c278-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="4c278-161">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4c278-161">Next steps</span></span>

<span data-ttu-id="4c278-162">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="4c278-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
