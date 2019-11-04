---
title: 'Découvrez comment créer un projet Q # avec le kit de développement quantique (QDK)'
description: 'Initialiser un projet pour le développement quantique avec QDK et Q # dans l’environnement de développement de votre choix'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444172"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="2bbfa-103">Créer un projet Q # dans votre environnement de développement</span><span class="sxs-lookup"><span data-stu-id="2bbfa-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="2bbfa-104">Découvrez comment créer un projet Q # avec QDK.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="2bbfa-105">Un projet Q # contient des fichiers Q # contenant du code Quantum, ainsi qu’un programme hôte pour exécuter le programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="2bbfa-106">Vous pouvez écrire le programme hôte dans des langages .NET C#tels que, ou dans Python.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="2bbfa-107">Vous pouvez également exécuter le code Q # dans un bloc-notes Jupyter à l’aide du noyau IQ #.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="2bbfa-108">Choisissez votre environnement et votre langage de développement dans les sections ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="2bbfa-109">Python</span><span class="sxs-lookup"><span data-stu-id="2bbfa-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="2bbfa-110">Blocs-notes Jupyter</span><span class="sxs-lookup"><span data-stu-id="2bbfa-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="2bbfa-111">C#avec Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bbfa-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="2bbfa-112">C#avec VS Code</span><span class="sxs-lookup"><span data-stu-id="2bbfa-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="2bbfa-113">C#avec la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="2bbfa-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="2bbfa-114">Créer un projet python</span><span class="sxs-lookup"><span data-stu-id="2bbfa-114">Create a Python project</span></span>

1. <span data-ttu-id="2bbfa-115">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2bbfa-115">Pre-requisites</span></span>

     * <span data-ttu-id="2bbfa-116">[Kit de développement quantique pour Python](xref:microsoft.quantum.install#develop-with-python)</span><span class="sxs-lookup"><span data-stu-id="2bbfa-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="2bbfa-117">Créez un dossier pour votre projet et accédez à ce dossier</span><span class="sxs-lookup"><span data-stu-id="2bbfa-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="2bbfa-118">Créez un fichier Q # nommé `Operation.qs`et ajoutez-y votre code Q #.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="2bbfa-119">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-119">For example:</span></span>

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

1. <span data-ttu-id="2bbfa-120">Créez un fichier d’hôte Python appelé `host.py` pour appeler votre opération Q #.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="2bbfa-121">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="2bbfa-122">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="2bbfa-123">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-123">Verify the output.</span></span> <span data-ttu-id="2bbfa-124">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="2bbfa-125">Vous pouvez maintenant continuer à développer votre programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="2bbfa-126">Créer un projet Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2bbfa-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="2bbfa-127">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2bbfa-127">Pre-requisites</span></span>

    * <span data-ttu-id="2bbfa-128">Le [Kit de développement quantique pour les blocs-notes Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="2bbfa-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="2bbfa-129">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="2bbfa-130">Accédez à l’URL affichée sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="2bbfa-131">Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="2bbfa-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="2bbfa-132">Une page Jupyter s’affiche dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="2bbfa-133">Dans l’onglet **fichiers** , sélectionnez **nouveau** > **Q #** pour créer un bloc-notes Jupyter avec un noyau q #.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="2bbfa-134">Ajoutez le code suivant à la première cellule du bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="2bbfa-135">Sélectionnez **cellule** > **exécuter les cellules** pour exécuter le bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="2bbfa-136">`SayHello` s’affiche bientôt dans la sortie de la cellule :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter cellule de bloc-notes avec le code Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="2bbfa-138">Lors de l’exécution dans des blocs-notes Jupyter, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="2bbfa-139">Dans une nouvelle cellule, Simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la `%simulate` Magic :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Cellule de bloc-notes Jupyter avec% simuler Magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="2bbfa-141">Vous devez voir le message imprimé à l’écran, ainsi que le résultat de l’opération que vous avez appelée (dans ce cas, vide).</span><span class="sxs-lookup"><span data-stu-id="2bbfa-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="2bbfa-142">Vous pouvez maintenant ajouter d’autres opérations Q # pour poursuivre le développement de votre Quantum.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="2bbfa-143">Créer un C# projet sur Windows à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bbfa-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="2bbfa-144">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2bbfa-144">Pre-requisites</span></span>

    * <span data-ttu-id="2bbfa-145">Le [Kit de développement quantique pour Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="2bbfa-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="2bbfa-146">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="2bbfa-146">Create a new Q# application</span></span>

    * <span data-ttu-id="2bbfa-147">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="2bbfa-148">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="2bbfa-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="2bbfa-149">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="2bbfa-150">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-150">Select **Next**</span></span>
    * <span data-ttu-id="2bbfa-151">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="2bbfa-152">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-152">Select **Create**</span></span>

1. <span data-ttu-id="2bbfa-153">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="2bbfa-153">Inspect the project</span></span>

    <span data-ttu-id="2bbfa-154">Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="2bbfa-155">Exécution de l’application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-155">Run the application</span></span>

    * <span data-ttu-id="2bbfa-156">Sélectionnez **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="2bbfa-157">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="2bbfa-158">Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bbfa-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="2bbfa-159">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="2bbfa-160">Créer un C# projet à l’aide de vs code</span><span class="sxs-lookup"><span data-stu-id="2bbfa-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="2bbfa-161">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2bbfa-161">Pre-requisites</span></span>

    * <span data-ttu-id="2bbfa-162">[Kit de développement quantique pour vs code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="2bbfa-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="2bbfa-163">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-163">Create a new project:</span></span>

    * <span data-ttu-id="2bbfa-164">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="2bbfa-165">Sélectionnez **Q # : créer un projet**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="2bbfa-166">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="2bbfa-167">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="2bbfa-168">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="2bbfa-168">Run the application:</span></span>

    * <span data-ttu-id="2bbfa-169">Accédez à **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="2bbfa-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="2bbfa-170">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2bbfa-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="2bbfa-171">Vous pouvez maintenant continuer votre développement quantique à l’aide de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="2bbfa-172">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="2bbfa-173">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2bbfa-174">Créer un C# projet à l’aide de l’outil en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="2bbfa-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2bbfa-175">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2bbfa-175">Pre-requisites</span></span>

    * <span data-ttu-id="2bbfa-176">[Kit de développement quantique pour la ligne de commande](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span><span class="sxs-lookup"><span data-stu-id="2bbfa-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="2bbfa-177">Créer une application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="2bbfa-178">Accédez au nouveau répertoire de l’application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="2bbfa-179">Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="2bbfa-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="2bbfa-180">Exécution de l’application</span><span class="sxs-lookup"><span data-stu-id="2bbfa-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="2bbfa-181">Vous devez normalement voir la sortie suivante : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2bbfa-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="2bbfa-182">Vous continuez maintenant votre développement Quantum, à l’aide d’outils en ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="2bbfa-183">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="2bbfa-183">What's next?</span></span>

<span data-ttu-id="2bbfa-184">Maintenant que vous avez créé un projet dans votre environnement préféré, vous pouvez continuer votre développement quantique.</span><span class="sxs-lookup"><span data-stu-id="2bbfa-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
