---
title: 'Découvrez comment créer un projet Q # avec le kit de développement quantique (QDK)'
description: 'Initialiser un projet pour le développement quantique avec QDK et Q # dans l’environnement de développement de votre choix'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578209"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="5e204-103">Créer un projet Q # dans votre environnement de développement</span><span class="sxs-lookup"><span data-stu-id="5e204-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="5e204-104">Découvrez comment créer un projet Q # avec QDK.</span><span class="sxs-lookup"><span data-stu-id="5e204-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="5e204-105">Un projet Q # contient des fichiers Q # contenant du code Quantum, ainsi qu’un programme hôte pour exécuter le programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="5e204-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="5e204-106">Vous pouvez écrire le programme hôte dans des langages .NET tels que C# ou dans Python.</span><span class="sxs-lookup"><span data-stu-id="5e204-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="5e204-107">Vous pouvez également exécuter le code Q # dans un Jupyter Notebook à l’aide du noyau IQ #.</span><span class="sxs-lookup"><span data-stu-id="5e204-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="5e204-108">Choisissez votre environnement et votre langage de développement dans les sections ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="5e204-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="5e204-109">Python</span><span class="sxs-lookup"><span data-stu-id="5e204-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="5e204-110">Notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="5e204-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="5e204-111">C# avec Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e204-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="5e204-112">C# avec VS Code</span><span class="sxs-lookup"><span data-stu-id="5e204-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="5e204-113">C# avec la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="5e204-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="5e204-114">Créer un projet Python</span><span class="sxs-lookup"><span data-stu-id="5e204-114">Create a Python project</span></span>

1. <span data-ttu-id="5e204-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5e204-115">Pre-requisites</span></span>

     * <span data-ttu-id="5e204-116">Installer le [Kit de développement Quantum pour Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="5e204-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="5e204-117">Créez un dossier pour votre projet et accédez à ce dossier</span><span class="sxs-lookup"><span data-stu-id="5e204-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="5e204-118">Créez un fichier Q # nommé `Operation.qs` et ajoutez-y votre code q #.</span><span class="sxs-lookup"><span data-stu-id="5e204-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="5e204-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5e204-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="5e204-120">Créez un fichier d’hôte Python appelé `host.py` pour appeler votre opération Q #.</span><span class="sxs-lookup"><span data-stu-id="5e204-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="5e204-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5e204-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="5e204-122">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="5e204-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="5e204-123">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="5e204-123">Verify the output.</span></span> <span data-ttu-id="5e204-124">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e204-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="5e204-125">Vous pouvez maintenant continuer à développer votre programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="5e204-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="5e204-126">Créer un projet Jupyter Notebook Q #</span><span class="sxs-lookup"><span data-stu-id="5e204-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="5e204-127">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5e204-127">Pre-requisites</span></span>

    * <span data-ttu-id="5e204-128">Installer le [Kit de développement quantique pour les blocs-notes Jupyter](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="5e204-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="5e204-129">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="5e204-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="5e204-130">Accédez à l’URL affichée sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="5e204-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="5e204-131">Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="5e204-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="5e204-132">Une page Jupyter s’affiche dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="5e204-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="5e204-133">Dans l’onglet **fichiers** , sélectionnez **nouveau**  >  **Q #** pour créer un Jupyter Notebook avec un noyau q #.</span><span class="sxs-lookup"><span data-stu-id="5e204-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="5e204-134">Ajoutez le code suivant à la première cellule du bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="5e204-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="5e204-135">Sélectionnez **cellule**  >  **exécuter les cellules** pour exécuter le bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="5e204-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="5e204-136">`SayHello`s’affiche bientôt dans la sortie de la cellule :</span><span class="sxs-lookup"><span data-stu-id="5e204-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter Notebook cellule avec le code Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="5e204-138">Lors de l’exécution dans des blocs-notes Jupyter, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="5e204-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="5e204-139">Dans une nouvelle cellule, simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la commande magic `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="5e204-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter Notebook cellule avec% simulateur magique](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="5e204-141">Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (vide dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="5e204-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="5e204-142">Vous pouvez maintenant ajouter d’autres opérations Q # pour poursuivre le développement de votre Quantum.</span><span class="sxs-lookup"><span data-stu-id="5e204-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="5e204-143">Créer un projet C# sur Windows à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e204-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="5e204-144">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5e204-144">Pre-requisites</span></span>

    * <span data-ttu-id="5e204-145">Installer l' [extension du kit de développement Quantum pour Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="5e204-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="5e204-146">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="5e204-146">Create a new Q# application</span></span>

    * <span data-ttu-id="5e204-147">Accéder au **fichier**  ->  **nouveau**  ->  **projet**</span><span class="sxs-lookup"><span data-stu-id="5e204-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="5e204-148">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="5e204-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="5e204-149">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="5e204-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="5e204-150">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5e204-150">Select **Next**</span></span>
    * <span data-ttu-id="5e204-151">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="5e204-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="5e204-152">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="5e204-152">Select **Create**</span></span>

1. <span data-ttu-id="5e204-153">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="5e204-153">Inspect the project</span></span>

    <span data-ttu-id="5e204-154">Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="5e204-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="5e204-155">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="5e204-155">Run the application</span></span>

    * <span data-ttu-id="5e204-156">Sélectionnez **Déboguer**  ->  **exécuter sans débogage**</span><span class="sxs-lookup"><span data-stu-id="5e204-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="5e204-157">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="5e204-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="5e204-158">Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e204-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="5e204-159">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="5e204-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="5e204-160">Créer un projet C#, à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="5e204-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="5e204-161">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5e204-161">Pre-requisites</span></span>

    * <span data-ttu-id="5e204-162">Installer l' [extension du kit de développement Quantum pour vs code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="5e204-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="5e204-163">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="5e204-163">Create a new project:</span></span>

    * <span data-ttu-id="5e204-164">Accéder à **View**la  ->  **palette de commandes** de la vue</span><span class="sxs-lookup"><span data-stu-id="5e204-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="5e204-165">Sélectionnez **Q # : créer un projet**</span><span class="sxs-lookup"><span data-stu-id="5e204-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="5e204-166">Sélectionner une **application console autonome**</span><span class="sxs-lookup"><span data-stu-id="5e204-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="5e204-167">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="5e204-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="5e204-168">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="5e204-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="5e204-169">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="5e204-169">Run the application:</span></span>

    * <span data-ttu-id="5e204-170">Accéder au **Terminal**  ->  **nouveau terminal**</span><span class="sxs-lookup"><span data-stu-id="5e204-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="5e204-171">Entrez `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="5e204-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="5e204-172">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5e204-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="5e204-173">Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5e204-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="5e204-174">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5e204-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="5e204-175">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="5e204-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5e204-176">Créer un projet C#, à l’aide de l' `dotnet` outil en ligne de commande</span><span class="sxs-lookup"><span data-stu-id="5e204-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="5e204-177">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5e204-177">Pre-requisites</span></span>

    * <span data-ttu-id="5e204-178">Installer le [Kit de développement Quantum pour la ligne de commande](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="5e204-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="5e204-179">Créer une application</span><span class="sxs-lookup"><span data-stu-id="5e204-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="5e204-180">Accédez au nouveau répertoire de l’application</span><span class="sxs-lookup"><span data-stu-id="5e204-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="5e204-181">Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="5e204-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="5e204-182">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="5e204-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="5e204-183">Vous devez normalement voir la sortie suivante : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5e204-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="5e204-184">Vous continuez maintenant votre développement Quantum, à l’aide d’outils en ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="5e204-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e204-185">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="5e204-185">Next steps</span></span>

<span data-ttu-id="5e204-186">Maintenant que vous avez créé un projet dans votre environnement préféré, vous pouvez continuer votre développement quantique.</span><span class="sxs-lookup"><span data-stu-id="5e204-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
