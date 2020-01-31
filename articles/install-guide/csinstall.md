---
title: 'Développer avec Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831016"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="4e643-102">Développer avec Q # +C#</span><span class="sxs-lookup"><span data-stu-id="4e643-102">Develop with Q# + C#</span></span>

<span data-ttu-id="4e643-103">Installez le QDK pour développer C# des programmes hôtes afin d’appeler des opérations Q #.</span><span class="sxs-lookup"><span data-stu-id="4e643-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="4e643-104">Q # est conçu pour fonctionner correctement avec les langages .NET, C#en particulier.</span><span class="sxs-lookup"><span data-stu-id="4e643-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="4e643-105">Vous pouvez utiliser ce couplage dans différents environnements de développement :</span><span class="sxs-lookup"><span data-stu-id="4e643-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="4e643-106">Q # + C# utilisation de Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="4e643-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="4e643-107">Q # + C# utilisation de Visual Studio code (Windows, Linux et Mac)</span><span class="sxs-lookup"><span data-stu-id="4e643-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="4e643-108">Q # + C# utilisation de l’outil de ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="4e643-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="4e643-109">Développer avec Q # + C# à l’aide de Visual Studio<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="4e643-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="4e643-110">Visual Studio offre un environnement riche pour le développement de programmes Q #.</span><span class="sxs-lookup"><span data-stu-id="4e643-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="4e643-111">L’extension Q # Visual Studio contient des modèles pour les fichiers et projets Q #, ainsi que la mise en surbrillance de la syntaxe, la saisie semi-automatique du code et la prise en charge IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4e643-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="4e643-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4e643-112">Pre-requisites</span></span>

    - <span data-ttu-id="4e643-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée</span><span class="sxs-lookup"><span data-stu-id="4e643-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="4e643-114">Installez l’extension Visual Studio pour Q#</span><span class="sxs-lookup"><span data-stu-id="4e643-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4e643-115">Télécharger et installer l' [extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4e643-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="4e643-116">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4e643-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4e643-117">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="4e643-117">Create a new Q# application</span></span>

        - <span data-ttu-id="4e643-118">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="4e643-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="4e643-119">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="4e643-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="4e643-120">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="4e643-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="4e643-121">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4e643-121">Select **Next**</span></span>
        - <span data-ttu-id="4e643-122">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="4e643-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="4e643-123">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="4e643-123">Select **Create**</span></span>

    - <span data-ttu-id="4e643-124">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="4e643-124">Inspect the project</span></span>

        <span data-ttu-id="4e643-125">Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="4e643-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="4e643-126">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="4e643-126">Run the application</span></span>

        - <span data-ttu-id="4e643-127">Sélectionnez **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="4e643-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4e643-128">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="4e643-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="4e643-129">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="4e643-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="4e643-130">Développer avec Q # + C# à l’aide de Visual Studio code<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="4e643-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="4e643-131">Visual Studio Code (VS Code) offre un environnement riche pour le développement de programmes Q # sur Windows, Linux et Mac.</span><span class="sxs-lookup"><span data-stu-id="4e643-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="4e643-132">L’extension Q # VS Code prend en charge la mise en surbrillance de la syntaxe Q #, la saisie semi-automatique du code et les extraits de code Q #.</span><span class="sxs-lookup"><span data-stu-id="4e643-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="4e643-133">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4e643-133">Pre-requisites</span></span>

   - [<span data-ttu-id="4e643-134">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4e643-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="4e643-135">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="4e643-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4e643-136">Installez l’extension VS Code pour Quantum</span><span class="sxs-lookup"><span data-stu-id="4e643-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4e643-137">Installez [l’extension VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="4e643-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="4e643-138">Installez les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="4e643-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="4e643-139">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="4e643-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4e643-140">Sélectionnez **Q # : installer les modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="4e643-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="4e643-141">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="4e643-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4e643-142">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4e643-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4e643-143">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="4e643-143">Create a new project:</span></span>

        - <span data-ttu-id="4e643-144">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="4e643-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="4e643-145">Sélectionnez **Q # : créer un projet**</span><span class="sxs-lookup"><span data-stu-id="4e643-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="4e643-146">Sélectionner une **application console autonome**</span><span class="sxs-lookup"><span data-stu-id="4e643-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="4e643-147">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="4e643-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="4e643-148">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="4e643-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="4e643-149">Si vous n’avez pas encore C# l’extension pour vs code installée, une fenêtre contextuelle s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4e643-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="4e643-150">Installez l’extension.</span><span class="sxs-lookup"><span data-stu-id="4e643-150">Install the extension.</span></span> 

    - <span data-ttu-id="4e643-151">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="4e643-151">Run the application:</span></span>

        - <span data-ttu-id="4e643-152">Accéder au **terminal** -> **nouveau terminal**</span><span class="sxs-lookup"><span data-stu-id="4e643-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="4e643-153">Entrez `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="4e643-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="4e643-154">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4e643-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="4e643-155">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4e643-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="4e643-156">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="4e643-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="4e643-157">Développer avec Q # + C# à l’aide de l’outil de ligne de commande `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="4e643-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="4e643-158">Bien entendu, vous pouvez également générer et exécuter des programmes Q# à partir de la ligne de commande en installant simplement le SDK .NET Core et les modèles de projet QDK.</span><span class="sxs-lookup"><span data-stu-id="4e643-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="4e643-159">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4e643-159">Pre-requisites</span></span>

    - [<span data-ttu-id="4e643-160">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="4e643-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4e643-161">Installez les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="4e643-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="4e643-162">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="4e643-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4e643-163">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4e643-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4e643-164">Créer une application</span><span class="sxs-lookup"><span data-stu-id="4e643-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="4e643-165">Accédez au nouveau répertoire de l’application</span><span class="sxs-lookup"><span data-stu-id="4e643-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="4e643-166">Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="4e643-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="4e643-167">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="4e643-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="4e643-168">Vous devez normalement voir la sortie suivante : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4e643-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="4e643-169">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="4e643-169">What's next?</span></span>

<span data-ttu-id="4e643-170">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="4e643-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
