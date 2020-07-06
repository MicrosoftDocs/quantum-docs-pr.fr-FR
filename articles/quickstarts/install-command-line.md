---
title: Développer avec des applications en ligne de commande Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884272"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="d0f04-102">Développer avec des applications en ligne de commande Q#</span><span class="sxs-lookup"><span data-stu-id="d0f04-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="d0f04-103">Les programmes Q# peuvent être exécutés seuls et sans pilote dans un langage hôte comme C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="d0f04-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0f04-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d0f04-104">Prerequisites</span></span>

- [<span data-ttu-id="d0f04-105">SDK .NET Core 3.1 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="d0f04-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="d0f04-106">Installation</span><span class="sxs-lookup"><span data-stu-id="d0f04-106">Installation</span></span>

<span data-ttu-id="d0f04-107">Bien que vous puissiez générer des applications en ligne de commande Q# dans n’importe quel IDE, nous vous recommandons d’utiliser Visual Studio Code (VS Code) ou Visual Studio IDE pour vos applications Q#.</span><span class="sxs-lookup"><span data-stu-id="d0f04-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="d0f04-108">Lorsque vous développez dans ces environnements, vous pouvez tirer parti des nombreuses fonctionnalités de l’extension QDK, comme les avertissements, la coloration syntaxique, les modèles de projets, etc.</span><span class="sxs-lookup"><span data-stu-id="d0f04-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="d0f04-109">Pour configurer VS Code :</span><span class="sxs-lookup"><span data-stu-id="d0f04-109">To configure VS Code:</span></span>

1. <span data-ttu-id="d0f04-110">Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="d0f04-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="d0f04-111">Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="d0f04-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d0f04-112">Pour configurer Visual Studio :</span><span class="sxs-lookup"><span data-stu-id="d0f04-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="d0f04-113">Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.</span><span class="sxs-lookup"><span data-stu-id="d0f04-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="d0f04-114">Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="d0f04-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="d0f04-115">Si vous souhaitez installer le QDK pour un autre environnement, entrez ceci sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="d0f04-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="d0f04-116">Développer avec Q#</span><span class="sxs-lookup"><span data-stu-id="d0f04-116">Develop with Q#</span></span>

<span data-ttu-id="d0f04-117">Suivez les instructions situées sous l’onglet correspondant à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d0f04-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="d0f04-118">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0f04-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d0f04-119">Installez les modèles de projet Q# :</span><span class="sxs-lookup"><span data-stu-id="d0f04-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="d0f04-120">Ouvrez Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d0f04-120">Open VS Code.</span></span>
2. <span data-ttu-id="d0f04-121">Cliquez sur **Affichage** -> **Palette de commandes**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="d0f04-122">Sélectionnez **Q# : Installer des modèles de projet**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="d0f04-123">Quand **Modèles de projet installés** s’affiche, le QDK est prêt à être utilisé avec vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="d0f04-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="d0f04-124">Pour créer un projet :</span><span class="sxs-lookup"><span data-stu-id="d0f04-124">To create a new project:</span></span>

1. <span data-ttu-id="d0f04-125">Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="d0f04-126">Cliquez sur **Application console autonome**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="d0f04-127">Accédez à l’emplacement où vous souhaitez enregistrer le projet, puis cliquez sur **Créer le projet**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="d0f04-128">Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="d0f04-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="d0f04-129">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="d0f04-129">Inspect the project.</span></span> <span data-ttu-id="d0f04-130">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="d0f04-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="d0f04-131">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="d0f04-131">To run the application:</span></span>
1. <span data-ttu-id="d0f04-132">Cliquez sur **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="d0f04-133">À l’invite du terminal, entrez `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="d0f04-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="d0f04-134">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d0f04-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="d0f04-135">Les espaces de travail avec plusieurs dossiers racine ne sont pas actuellement pris en charge par l’extension VS Code Q#.</span><span class="sxs-lookup"><span data-stu-id="d0f04-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="d0f04-136">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="d0f04-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="d0f04-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0f04-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="d0f04-138">Vérifiez votre installation de Visual Studio en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="d0f04-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="d0f04-139">Pour créer une application Q# :</span><span class="sxs-lookup"><span data-stu-id="d0f04-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="d0f04-140">Ouvrez Visual Studio, puis cliquez sur **Fichier** -> **Nouveau** -> **Projet**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="d0f04-141">Tapez `Q#` dans la zone de recherche, sélectionnez **Application Q#** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="d0f04-142">Entrez un nom et un emplacement pour votre application, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="d0f04-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="d0f04-143">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="d0f04-143">Inspect the project.</span></span> <span data-ttu-id="d0f04-144">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="d0f04-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="d0f04-145">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="d0f04-145">To run the application:</span></span>
1. <span data-ttu-id="d0f04-146">Sélectionnez **Déboguer** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="d0f04-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="d0f04-147">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="d0f04-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="d0f04-148">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="d0f04-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="d0f04-149">Autres éditeurs avec la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="d0f04-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="d0f04-150">Vérifiez votre installation en créant une application `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="d0f04-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="d0f04-151">Créez une application :</span><span class="sxs-lookup"><span data-stu-id="d0f04-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="d0f04-152">Accédez au répertoire de l’application :</span><span class="sxs-lookup"><span data-stu-id="d0f04-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="d0f04-153">Ce répertoire doit maintenant contenir un fichier `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="d0f04-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="d0f04-154">Vous pouvez modifier ce modèle avec un éditeur de texte et le remplacer par vos propres applications quantiques.</span><span class="sxs-lookup"><span data-stu-id="d0f04-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="d0f04-155">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="d0f04-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="d0f04-156">Le texte suivant doit s’afficher : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d0f04-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="d0f04-157">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d0f04-157">Next steps</span></span>

<span data-ttu-id="d0f04-158">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="d0f04-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
