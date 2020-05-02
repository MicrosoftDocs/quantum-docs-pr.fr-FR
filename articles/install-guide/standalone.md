---
title: 'Exécuter les programmes Q # sans pilote ni langue hôte'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706799"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="d3fd1-102">Q # applications en ligne de commande</span><span class="sxs-lookup"><span data-stu-id="d3fd1-102">Q# Command Line Applications</span></span>

<span data-ttu-id="d3fd1-103">Les programmes Q # peuvent être exécutés seuls, sans pilote dans un langage hôte tel que C#, F # ou python.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="d3fd1-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d3fd1-104">Pre-requisites</span></span>

- [<span data-ttu-id="d3fd1-105">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d3fd1-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="d3fd1-106">Installation</span><span class="sxs-lookup"><span data-stu-id="d3fd1-106">Installation</span></span>

<span data-ttu-id="d3fd1-107">Bien que vous puissiez créer des applications en ligne de commande Q # dans n’importe quel IDE, nous vous recommandons vivement d’utiliser Visual Studio Code (VS Code) ou l’IDE de Visual Studio pour vos applications Q #.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="d3fd1-108">En utilisant VS Code ou Visual Studio et l’extension QDK Visual Studio Code vous accédez à des fonctionnalités plus riches.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="d3fd1-109">Installer [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac)</span><span class="sxs-lookup"><span data-stu-id="d3fd1-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="d3fd1-110">Installez l' [extension QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) ou</span><span class="sxs-lookup"><span data-stu-id="d3fd1-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="d3fd1-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée</span><span class="sxs-lookup"><span data-stu-id="d3fd1-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="d3fd1-112">Télécharger et installer l' [extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="d3fd1-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="d3fd1-113">Développer avec Q # à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="d3fd1-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="d3fd1-114">Installez les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="d3fd1-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="d3fd1-115">Accéder à la**palette de commandes** de la **vue** -> </span><span class="sxs-lookup"><span data-stu-id="d3fd1-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="d3fd1-116">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="d3fd1-117">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="d3fd1-118">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="d3fd1-118">Create a new project:</span></span>
  - <span data-ttu-id="d3fd1-119">Accéder à la**palette de commandes** de la **vue** -> </span><span class="sxs-lookup"><span data-stu-id="d3fd1-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="d3fd1-120">Sélectionnez **Q # : créer un projet**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="d3fd1-121">Sélectionner une **application console autonome**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="d3fd1-122">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="d3fd1-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="d3fd1-123">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="d3fd1-124">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="d3fd1-124">Inspect the project</span></span>
  - <span data-ttu-id="d3fd1-125">Vous devez voir un fichier appelé `Program.qs` créé, qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d3fd1-126">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="d3fd1-126">Run the application:</span></span>
  - <span data-ttu-id="d3fd1-127">Accéder au **Terminal** -> **nouveau terminal**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="d3fd1-128">Entrez `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="d3fd1-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="d3fd1-129">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d3fd1-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="d3fd1-130">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="d3fd1-131">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="d3fd1-132">Développer avec Q # à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d3fd1-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="d3fd1-133">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="d3fd1-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="d3fd1-134">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="d3fd1-134">Create a new Q# application</span></span>
  - <span data-ttu-id="d3fd1-135">Accéder au **fichier** -> **nouveau** -> **projet**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="d3fd1-136">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="d3fd1-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="d3fd1-137">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="d3fd1-138">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-138">Select **Next**</span></span>
  - <span data-ttu-id="d3fd1-139">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="d3fd1-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="d3fd1-140">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-140">Select **Create**</span></span>

- <span data-ttu-id="d3fd1-141">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="d3fd1-141">Inspect the project</span></span>
  - <span data-ttu-id="d3fd1-142">Vous devez voir qu’un fichier appelé `Program.qs` a été créé, qui est un programme Q # qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d3fd1-143">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="d3fd1-143">Run the application</span></span>
  - <span data-ttu-id="d3fd1-144">Sélectionnez **Déboguer** -> **exécuter sans débogage**</span><span class="sxs-lookup"><span data-stu-id="d3fd1-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="d3fd1-145">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="d3fd1-146">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="d3fd1-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="d3fd1-147">Quelle est l’étape suivante ?</span><span class="sxs-lookup"><span data-stu-id="d3fd1-147">What's next?</span></span>

<span data-ttu-id="d3fd1-148">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="d3fd1-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
