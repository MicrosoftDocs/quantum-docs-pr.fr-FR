---
title: 'Développer avec les applications en ligne de commande Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426438"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="1afc6-102">Développer avec les applications en ligne de commande Q #</span><span class="sxs-lookup"><span data-stu-id="1afc6-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="1afc6-103">Les programmes Q # peuvent être exécutés seuls, sans pilote dans un langage hôte tel que C#, F # ou python.</span><span class="sxs-lookup"><span data-stu-id="1afc6-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1afc6-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1afc6-104">Pre-requisites</span></span>

- [<span data-ttu-id="1afc6-105">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="1afc6-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="1afc6-106">Installation</span><span class="sxs-lookup"><span data-stu-id="1afc6-106">Installation</span></span>

<span data-ttu-id="1afc6-107">Bien que vous puissiez générer des applications en ligne de commande Q # dans n’importe quel IDE, nous vous recommandons d’utiliser Visual Studio Code (VS Code) ou IDE de Visual Studio pour vos applications Q #.</span><span class="sxs-lookup"><span data-stu-id="1afc6-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="1afc6-108">Le développement de ces outils permet d’accéder à des fonctionnalités riches.</span><span class="sxs-lookup"><span data-stu-id="1afc6-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="1afc6-109">Pour configurer VS Code :</span><span class="sxs-lookup"><span data-stu-id="1afc6-109">To configure VS Code:</span></span>

1. <span data-ttu-id="1afc6-110">Téléchargez et installez [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="1afc6-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="1afc6-111">Installez [Microsoft QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="1afc6-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="1afc6-112">Pour configurer Visual Studio :</span><span class="sxs-lookup"><span data-stu-id="1afc6-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="1afc6-113">Téléchargez et installez [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 ou version ultérieure, avec la charge de travail développement multiplateforme .net Core activée.</span><span class="sxs-lookup"><span data-stu-id="1afc6-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="1afc6-114">Téléchargez et installez [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="1afc6-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="1afc6-115">Développer avec Q # à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="1afc6-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="1afc6-116">Installez les modèles de projet Q # :</span><span class="sxs-lookup"><span data-stu-id="1afc6-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="1afc6-117">Ouvrez Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1afc6-117">Open VS Code.</span></span>
2. <span data-ttu-id="1afc6-118">Cliquez sur **Afficher**la  ->  **palette de commandes**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="1afc6-119">Sélectionnez **Q # : installer les modèles de projet**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="1afc6-120">Lorsque les **modèles de projet installés avec succès** s’affichent, le QDK est prêt à être utilisé avec vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="1afc6-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="1afc6-121">Pour créer un nouveau projet :</span><span class="sxs-lookup"><span data-stu-id="1afc6-121">To create a new project:</span></span>

1. <span data-ttu-id="1afc6-122">Cliquez sur **Afficher**la  ->  **palette de commandes** et sélectionnez **Q # : créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="1afc6-123">Cliquez sur **application console autonome**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="1afc6-124">Accédez à l’emplacement où enregistrer le projet, puis cliquez sur **créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="1afc6-125">Lorsque le projet est correctement créé, cliquez sur **ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="1afc6-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="1afc6-126">Inspectez le projet.</span><span class="sxs-lookup"><span data-stu-id="1afc6-126">Inspect the project.</span></span> <span data-ttu-id="1afc6-127">Vous devez voir un fichier source nommé `Program.qs` , qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="1afc6-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1afc6-128">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="1afc6-128">To run the application:</span></span>
1. <span data-ttu-id="1afc6-129">Cliquez sur **Terminal**  ->  **nouveau terminal**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="1afc6-130">À l’invite du terminal, entrez `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="1afc6-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="1afc6-131">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1afc6-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="1afc6-132">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension VS Code Q #.</span><span class="sxs-lookup"><span data-stu-id="1afc6-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="1afc6-133">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="1afc6-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="1afc6-134">Développer avec Q # à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1afc6-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="1afc6-135">Vérifiez votre installation de Visual Studio en créant une application Q # `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="1afc6-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="1afc6-136">Pour créer une nouvelle application Q # :</span><span class="sxs-lookup"><span data-stu-id="1afc6-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="1afc6-137">Ouvrez Visual Studio et cliquez sur **fichier**  ->  **nouveau**  ->  **projet**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="1afc6-138">Tapez `Q#` dans la zone de recherche, sélectionnez **Q # application** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="1afc6-139">Entrez un nom et un emplacement pour votre application, puis cliquez sur **créer**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="1afc6-140">Inspectez le projet.</span><span class="sxs-lookup"><span data-stu-id="1afc6-140">Inspect the project.</span></span> <span data-ttu-id="1afc6-141">Vous devez voir un fichier source nommé `Program.qs` , qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="1afc6-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1afc6-142">Pour exécuter l’application :</span><span class="sxs-lookup"><span data-stu-id="1afc6-142">To run the application:</span></span>
1. <span data-ttu-id="1afc6-143">Sélectionnez **Déboguer**  ->  **exécuter sans débogage**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="1afc6-144">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="1afc6-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="1afc6-145">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans l’un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="1afc6-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="1afc6-146">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="1afc6-146">Next steps</span></span>

<span data-ttu-id="1afc6-147">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="1afc6-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
