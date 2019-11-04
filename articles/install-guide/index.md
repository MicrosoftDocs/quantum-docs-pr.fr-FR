---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2a098d89f13278d7137bf182a184a74afb9393be
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462874"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="21bc7-102">Installer le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="21bc7-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="21bc7-103">Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="21bc7-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="21bc7-104">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="21bc7-104">The QDK consists of:</span></span>

- <span data-ttu-id="21bc7-105">le langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="21bc7-105">the Q# programming language</span></span>
- <span data-ttu-id="21bc7-106">un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="21bc7-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="21bc7-107">une application hôte (écrite en Python ou en langage .NET) qui exécute des opérations quantiques écrites en Q#</span><span class="sxs-lookup"><span data-stu-id="21bc7-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="21bc7-108">des outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="21bc7-108">tools to facilitate your development</span></span>

<span data-ttu-id="21bc7-109">Selon l’environnement de développement choisi, il existe différentes étapes d’installation.</span><span class="sxs-lookup"><span data-stu-id="21bc7-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="21bc7-110">Choisissez votre environnement dans les sections ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="21bc7-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="21bc7-111">Développer avec Python</span><span class="sxs-lookup"><span data-stu-id="21bc7-111">Develop with Python</span></span>

<span data-ttu-id="21bc7-112">Le package qsharp pour Python facilite la simulation des opérations et des fonctions Q# dans Python.</span><span class="sxs-lookup"><span data-stu-id="21bc7-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="21bc7-113">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="21bc7-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="21bc7-114">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21bc7-114">Pre-requisites</span></span>

    - <span data-ttu-id="21bc7-115">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="21bc7-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="21bc7-116">Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="21bc7-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="21bc7-117">SDK .NET Core 3.0 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="21bc7-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="21bc7-118">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="21bc7-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="21bc7-119">Installez le package `qsharp`</span><span class="sxs-lookup"><span data-stu-id="21bc7-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="21bc7-120">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="21bc7-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="21bc7-121">Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="21bc7-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="21bc7-122">Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :</span><span class="sxs-lookup"><span data-stu-id="21bc7-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="21bc7-123">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="21bc7-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="21bc7-124">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="21bc7-124">Verify the output.</span></span> <span data-ttu-id="21bc7-125">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="21bc7-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="21bc7-126">Développer avec des notebooks Jupyter</span><span class="sxs-lookup"><span data-stu-id="21bc7-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="21bc7-127">Particulièrement appréciés des universités, laboratoires scientifiques et structures de programmation collaborative en ligne, les notebooks Jupyter assurent l’exécution de code sur place (y compris, désormais, du code Q#) et permettent d’utiliser des instructions, des notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="21bc7-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="21bc7-128">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="21bc7-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="21bc7-129">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="21bc7-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="21bc7-130">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21bc7-130">Pre-requisites</span></span>

    - <span data-ttu-id="21bc7-131">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="21bc7-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="21bc7-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="21bc7-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="21bc7-133">SDK .NET Core 3.0 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="21bc7-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="21bc7-134">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="21bc7-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="21bc7-135">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="21bc7-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="21bc7-136">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="21bc7-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="21bc7-137">Accédez à l’URL affichée sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="21bc7-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="21bc7-138">Par exemple : [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="21bc7-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="21bc7-139">Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="21bc7-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="21bc7-140">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="21bc7-140">Run this cell of the notebook:</span></span>

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="21bc7-142">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="21bc7-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="21bc7-143">Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="21bc7-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="21bc7-144">Dans une nouvelle cellule, simulez l’exécution sur un ordinateur quantique de l’opération que vous venez de créer à l’aide de la commande magic `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="21bc7-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="21bc7-146">Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (vide dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="21bc7-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="21bc7-147">Développer en C# sur Windows, à l’aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21bc7-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="21bc7-148">Visual Studio offre un environnement complet pour le développement de programmes Q# et notamment de puissantes fonctionnalités telles que la complétion de code et la mise en surbrillance de la syntaxe, qui guident le développeur dans la création d’applications.</span><span class="sxs-lookup"><span data-stu-id="21bc7-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="21bc7-149">L’extension Visual Studio Q# propose des modèles pour les fichiers et projets Q#, ainsi que la mise en surbrillance de la syntaxe et la prise en charge d’IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="21bc7-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="21bc7-150">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21bc7-150">Pre-requisites</span></span>

    - <span data-ttu-id="21bc7-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, avec la charge de travail de développement multiplateforme .NET Core activée</span><span class="sxs-lookup"><span data-stu-id="21bc7-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="21bc7-152">Installez l’extension Visual Studio pour Q#</span><span class="sxs-lookup"><span data-stu-id="21bc7-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="21bc7-153">Téléchargez l’[extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="21bc7-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="21bc7-154">Ajoutez l’extension à Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21bc7-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="21bc7-155">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="21bc7-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="21bc7-156">Créez une application en Q#</span><span class="sxs-lookup"><span data-stu-id="21bc7-156">Create a new Q# application</span></span>

        - <span data-ttu-id="21bc7-157">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="21bc7-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="21bc7-158">Saisissez `Q#` dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="21bc7-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="21bc7-159">Sélectionnez **Application Q#**</span><span class="sxs-lookup"><span data-stu-id="21bc7-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="21bc7-160">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="21bc7-160">Select **Next**</span></span>
        - <span data-ttu-id="21bc7-161">Choisissez un nom et un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="21bc7-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="21bc7-162">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="21bc7-162">Select **Create**</span></span>

    - <span data-ttu-id="21bc7-163">Examinez le projet</span><span class="sxs-lookup"><span data-stu-id="21bc7-163">Inspect the project</span></span>

        <span data-ttu-id="21bc7-164">Vous devriez voir que deux fichiers ont été créés : `Driver.cs`, qui est l’application hôte en C# ; et `Operation.qs`, qui est un programme en Q# qui définit une opération simple pour imprimer un message sur la console.</span><span class="sxs-lookup"><span data-stu-id="21bc7-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="21bc7-165">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="21bc7-165">Run the application</span></span>

        - <span data-ttu-id="21bc7-166">Sélectionnez **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="21bc7-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="21bc7-167">Vous devriez voir le texte `Hello quantum world!` imprimé dans une fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="21bc7-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="21bc7-168">Si vous avez plusieurs projets dans une solution Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="21bc7-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="21bc7-169">Développer en C# avec Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="21bc7-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="21bc7-170">Visual Studio Code (VS Code) apporte un environnement complet pour le développement de programmes Q# dans de nombreux environnements informatiques, notamment Windows, Linux et Mac. Il offre de puissantes fonctionnalités telles que la complétion de code et la mise en surbrillance de la syntaxe, qui guident le développeur dans la création d’applications.</span><span class="sxs-lookup"><span data-stu-id="21bc7-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="21bc7-171">L’extension VS Code Q# assure la mise en surbrillance de la syntaxe et offre des extraits de code Q#.</span><span class="sxs-lookup"><span data-stu-id="21bc7-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="21bc7-172">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21bc7-172">Pre-requisites</span></span>

   - [<span data-ttu-id="21bc7-173">Code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21bc7-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="21bc7-174">SDK .NET Core 3.0 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="21bc7-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="21bc7-175">Installez l’extension VS Code pour Quantum</span><span class="sxs-lookup"><span data-stu-id="21bc7-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="21bc7-176">Installez [l’extension VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="21bc7-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="21bc7-177">Installez les modèles de projet Quantum :</span><span class="sxs-lookup"><span data-stu-id="21bc7-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="21bc7-178">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="21bc7-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="21bc7-179">Sélectionnez **Q# : Installer des modèles de projet**</span><span class="sxs-lookup"><span data-stu-id="21bc7-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="21bc7-180">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="21bc7-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="21bc7-181">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="21bc7-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="21bc7-182">Créer un projet :</span><span class="sxs-lookup"><span data-stu-id="21bc7-182">Create a new project:</span></span>

        - <span data-ttu-id="21bc7-183">Accédez à **Affichage** -> **Palette de commandes**</span><span class="sxs-lookup"><span data-stu-id="21bc7-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="21bc7-184">Sélectionnez **Q# : Créer un projet**</span><span class="sxs-lookup"><span data-stu-id="21bc7-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="21bc7-185">Accédez à l’emplacement du système de fichiers dans lequel vous souhaitez créer l’application</span><span class="sxs-lookup"><span data-stu-id="21bc7-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="21bc7-186">Une fois le projet créé, cliquez sur le bouton **Ouvrir un nouveau projet…**</span><span class="sxs-lookup"><span data-stu-id="21bc7-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="21bc7-187">Exécutez l'application :</span><span class="sxs-lookup"><span data-stu-id="21bc7-187">Run the application:</span></span>

        - <span data-ttu-id="21bc7-188">Accédez à **Débogage** -> **Démarrer sans débogage**</span><span class="sxs-lookup"><span data-stu-id="21bc7-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="21bc7-189">Le texte suivant devrait apparaître dans la fenêtre de sortie `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="21bc7-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="21bc7-190">Les espaces de travail avec plusieurs dossiers racine ne sont actuellement pas pris en charge par l’extension Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="21bc7-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="21bc7-191">Si vous avez plusieurs projets dans un espace de travail VS Code, tous les projets doivent être contenus dans le même dossier racine.</span><span class="sxs-lookup"><span data-stu-id="21bc7-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="21bc7-192">Développer en C#, à l’aide du programme en ligne de commande `dotnet`</span><span class="sxs-lookup"><span data-stu-id="21bc7-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="21bc7-193">Bien entendu, vous pouvez également générer et exécuter des programmes Q# à partir de la ligne de commande en installant simplement le SDK .NET Core et les modèles de projet QDK.</span><span class="sxs-lookup"><span data-stu-id="21bc7-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="21bc7-194">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21bc7-194">Pre-requisites</span></span>

    - [<span data-ttu-id="21bc7-195">SDK .NET Core 3.0 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="21bc7-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="21bc7-196">Installez les modèles de projet Quantum pour .NET</span><span class="sxs-lookup"><span data-stu-id="21bc7-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="21bc7-197">Le Quantum Development Kit est maintenant installé et prêt à être utilisé dans vos propres applications et bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="21bc7-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="21bc7-198">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="21bc7-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="21bc7-199">Créer une application</span><span class="sxs-lookup"><span data-stu-id="21bc7-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="21bc7-200">Accédez au nouveau répertoire de l’application</span><span class="sxs-lookup"><span data-stu-id="21bc7-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="21bc7-201">Vous devriez voir que deux fichiers ont été créés, ainsi que les fichiers projet de l’application : un fichier en Q# (`Operation.qs`) et un fichier hôte en C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="21bc7-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="21bc7-202">Exécution de l'application</span><span class="sxs-lookup"><span data-stu-id="21bc7-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="21bc7-203">Vous devez normalement voir la sortie suivante : `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="21bc7-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="21bc7-204">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="21bc7-204">What's next?</span></span>

<span data-ttu-id="21bc7-205">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="21bc7-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
