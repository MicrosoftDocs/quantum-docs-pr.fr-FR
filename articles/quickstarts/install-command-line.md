---
title: Développer avec des applications en ligne de commande Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274121"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="5c91a-102">Développer avec des applications en ligne de commande Q#</span><span class="sxs-lookup"><span data-stu-id="5c91a-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="5c91a-103">Les programmes Q# peuvent être exécutés seuls et sans pilote dans un langage hôte comme C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="5c91a-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c91a-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="5c91a-104">Prerequisites</span></span>

- [<span data-ttu-id="5c91a-105">SDK .NET Core 3.1 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="5c91a-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="5c91a-106">Installation</span><span class="sxs-lookup"><span data-stu-id="5c91a-106">Installation</span></span>

<span data-ttu-id="5c91a-107">Bien que vous puissiez générer des applications en ligne de commande Q# dans n’importe quel IDE, nous vous recommandons d’utiliser Visual Studio Code (VS Code) ou Visual Studio IDE pour vos applications Q#.</span><span class="sxs-lookup"><span data-stu-id="5c91a-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="5c91a-108">Le développement dans ces outils vous donne accès à de riches fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="5c91a-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="5c91a-109">Pour configurer VS Code :</span><span class="sxs-lookup"><span data-stu-id="5c91a-109">To configure VS Code:</span></span>

1. <span data-ttu-id="5c91a-110">Téléchargez et installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="5c91a-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="5c91a-111">Installez le [Microsoft QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="5c91a-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="5c91a-112">Pour configurer Visual Studio :</span><span class="sxs-lookup"><span data-stu-id="5c91a-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="5c91a-113">Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou ultérieur avec la charge de travail de développement multiplateforme .NET Core activée.</span><span class="sxs-lookup"><span data-stu-id="5c91a-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="5c91a-114">Téléchargez et installez le [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="5c91a-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="5c91a-115">Développer en Q# à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="5c91a-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="5c91a-116">Installez les modèles de projet Q# :</span><span class="sxs-lookup"><span data-stu-id="5c91a-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="5c91a-117">Ouvrez Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5c91a-117">Open VS Code.</span></span>
2. <span data-ttu-id="5c91a-118">Cliquez sur **Affichage** -> **Palette de commandes**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="5c91a-119">Sélectionnez **Q# : Installer des modèles de projet**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="5c91a-120">Quand **Modèles de projet installés** s’affiche, le QDK est prêt à être utilisé avec vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="5c91a-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="5c91a-121">Pour créer un projet :</span><span class="sxs-lookup"><span data-stu-id="5c91a-121">To create a new project:</span></span>

1. <span data-ttu-id="5c91a-122">Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="5c91a-123">Cliquez sur **Application console autonome**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="5c91a-124">Accédez à l’emplacement où vous souhaitez enregistrer le projet, puis cliquez sur **Créer le projet**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="5c91a-125">Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="5c91a-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="5c91a-126">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="5c91a-126">Inspect the project.</span></span> <span data-ttu-id="5c91a-127">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="5c91a-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="5c91a-128">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="5c91a-128">To run the application:</span></span>
1. <span data-ttu-id="5c91a-129">Cliquez sur **Terminal** -> **Nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="5c91a-130">À l’invite du terminal, entrez `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="5c91a-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="5c91a-131">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5c91a-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="5c91a-132">Les espaces de travail avec plusieurs dossiers racine ne sont pas actuellement pris en charge par l’extension VS Code Q#.</span><span class="sxs-lookup"><span data-stu-id="5c91a-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="5c91a-133">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="5c91a-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="5c91a-134">Développer en Q# avec Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c91a-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="5c91a-135">Vérifiez votre installation de Visual Studio en créant une application Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="5c91a-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="5c91a-136">Pour créer une application Q# :</span><span class="sxs-lookup"><span data-stu-id="5c91a-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="5c91a-137">Ouvrez Visual Studio, puis cliquez sur **Fichier** -> **Nouveau** -> **Projet**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="5c91a-138">Tapez `Q#` dans la zone de recherche, sélectionnez **Application Q#** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="5c91a-139">Entrez un nom et un emplacement pour votre application, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5c91a-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="5c91a-140">Examinez le projet.</span><span class="sxs-lookup"><span data-stu-id="5c91a-140">Inspect the project.</span></span> <span data-ttu-id="5c91a-141">Vous devriez voir un fichier source nommé `Program.qs`. Il s’agit d’un programme Q# qui définit une opération simple pour afficher un message dans la console.</span><span class="sxs-lookup"><span data-stu-id="5c91a-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="5c91a-142">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="5c91a-142">To run the application:</span></span>
1. <span data-ttu-id="5c91a-143">Sélectionnez **Déboguer** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="5c91a-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="5c91a-144">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="5c91a-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="5c91a-145">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="5c91a-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="5c91a-146">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="5c91a-146">Next steps</span></span>

<span data-ttu-id="5c91a-147">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="5c91a-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
