---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035303"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e23e1-102">Installer le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="e23e1-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e23e1-103">Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="e23e1-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="e23e1-104">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e23e1-104">The QDK consists of:</span></span>

- <span data-ttu-id="e23e1-105">le langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="e23e1-105">the Q# programming language</span></span>
- <span data-ttu-id="e23e1-106">un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="e23e1-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="e23e1-107">une application hôte (écrite en Python ou en langage .NET) qui exécute des opérations quantiques écrites en Q#</span><span class="sxs-lookup"><span data-stu-id="e23e1-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="e23e1-108">des outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="e23e1-108">tools to facilitate your development</span></span>

<span data-ttu-id="e23e1-109">Selon l’environnement de développement choisi, il existe différentes étapes d’installation.</span><span class="sxs-lookup"><span data-stu-id="e23e1-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="e23e1-110">Choisissez votre environnement dans les sections ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e23e1-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="e23e1-111">Développer avec Python</span><span class="sxs-lookup"><span data-stu-id="e23e1-111">Develop with Python</span></span>

1. <span data-ttu-id="e23e1-112">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e23e1-112">Pre-requisites</span></span>

    - <span data-ttu-id="e23e1-113">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="e23e1-114">Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="e23e1-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="e23e1-115">Kit SDK .NET Core 2.1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="e23e1-116">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e23e1-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="e23e1-117">Installez le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="e23e1-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="e23e1-118">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e23e1-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e23e1-119">Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="e23e1-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="e23e1-120">Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :</span><span class="sxs-lookup"><span data-stu-id="e23e1-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="e23e1-121">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="e23e1-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="e23e1-122">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="e23e1-122">Verify the output.</span></span> <span data-ttu-id="e23e1-123">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e23e1-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="e23e1-124">Développer avec des notebooks Jupyter</span><span class="sxs-lookup"><span data-stu-id="e23e1-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="e23e1-125">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e23e1-125">Pre-requisites</span></span>

    - <span data-ttu-id="e23e1-126">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="e23e1-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="e23e1-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="e23e1-128">Kit SDK .NET Core 2.1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="e23e1-129">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e23e1-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="e23e1-130">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e23e1-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e23e1-131">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="e23e1-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="e23e1-132">Accédez à l’URL affichée sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e23e1-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="e23e1-133">Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="e23e1-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="e23e1-134">Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="e23e1-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="e23e1-135">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="e23e1-135">Run this cell of the notebook:</span></span>

        ![Cellule du notebook Jupyter](~/media/install-guide-jupyter.png)

        <span data-ttu-id="e23e1-137">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="e23e1-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="e23e1-138">Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="e23e1-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="e23e1-139">Développer en C# sur Windows, à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e23e1-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="e23e1-140">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e23e1-140">Pre-requisites</span></span>

    - <span data-ttu-id="e23e1-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée</span><span class="sxs-lookup"><span data-stu-id="e23e1-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="e23e1-142">Installez l’extension Visual Studio pour Q#</span><span class="sxs-lookup"><span data-stu-id="e23e1-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="e23e1-143">Téléchargez l’[extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="e23e1-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="e23e1-144">Ajoutez l’extension à Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e23e1-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="e23e1-145">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e23e1-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e23e1-146">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="e23e1-146">Create a new Q# application</span></span>

        - <span data-ttu-id="e23e1-147">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="e23e1-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="e23e1-148">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="e23e1-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="e23e1-149">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="e23e1-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="e23e1-150">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e23e1-150">Select **Next**</span></span>
        - <span data-ttu-id="e23e1-151">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="e23e1-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="e23e1-152">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="e23e1-152">Select **Create**</span></span>

    - <span data-ttu-id="e23e1-153">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="e23e1-153">Inspect the project</span></span>

        <span data-ttu-id="e23e1-154">Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="e23e1-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="e23e1-155">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="e23e1-155">Run the application</span></span>

        - <span data-ttu-id="e23e1-156">Sélectionnez **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="e23e1-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="e23e1-157">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="e23e1-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="e23e1-158">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="e23e1-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="e23e1-159">Développer en C#, à l’aide de VS Code</span><span class="sxs-lookup"><span data-stu-id="e23e1-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="e23e1-160">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e23e1-160">Pre-requisites</span></span>

   - [<span data-ttu-id="e23e1-161">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e23e1-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="e23e1-162">Kit SDK .NET Core 2.1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="e23e1-163">Installez l’extension VS Code pour Quantum</span><span class="sxs-lookup"><span data-stu-id="e23e1-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="e23e1-164">Installez [l’extension VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="e23e1-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="e23e1-165">Installez les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="e23e1-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="e23e1-166">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="e23e1-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="e23e1-167">Sélectionnez **Q# : Installer des modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="e23e1-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="e23e1-168">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="e23e1-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="e23e1-169">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e23e1-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e23e1-170">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="e23e1-170">Create a new project:</span></span>

        - <span data-ttu-id="e23e1-171">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="e23e1-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="e23e1-172">Sélectionnez **Q# : Créer un projet**</span><span class="sxs-lookup"><span data-stu-id="e23e1-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="e23e1-173">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="e23e1-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="e23e1-174">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="e23e1-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="e23e1-175">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="e23e1-175">Run the application:</span></span>

        - <span data-ttu-id="e23e1-176">Accédez à **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="e23e1-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="e23e1-177">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="e23e1-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="e23e1-178">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e23e1-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="e23e1-179">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="e23e1-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="e23e1-180">Développer en C#, à l’aide du programme en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="e23e1-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="e23e1-181">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e23e1-181">Pre-requisites</span></span>

    - [<span data-ttu-id="e23e1-182">Kit SDK .NET Core 2.1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e23e1-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="e23e1-183">Installez les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="e23e1-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="e23e1-184">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="e23e1-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="e23e1-185">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e23e1-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e23e1-186">Créer une application</span><span class="sxs-lookup"><span data-stu-id="e23e1-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="e23e1-187">Accédez au nouveau répertoire de l’application</span><span class="sxs-lookup"><span data-stu-id="e23e1-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="e23e1-188">Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="e23e1-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="e23e1-189">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="e23e1-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="e23e1-190">Vous devez normalement voir la sortie suivante : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="e23e1-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="e23e1-191">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="e23e1-191">What's next?</span></span>

<span data-ttu-id="e23e1-192">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="e23e1-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
