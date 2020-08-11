---
title: Développer en Q# et Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 01a5c31a7a920a69f4f90701d370f3a772d2c4d2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866738"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="03ab0-102">Développer en Q# et Python</span><span class="sxs-lookup"><span data-stu-id="03ab0-102">Develop with Q# and Python</span></span>

<span data-ttu-id="03ab0-103">Installez le QDK pour développer des programmes hôtes Python afin d’appeler des opérations en Q#.</span><span class="sxs-lookup"><span data-stu-id="03ab0-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="03ab0-104">Installer le package Python `qsharp`</span><span class="sxs-lookup"><span data-stu-id="03ab0-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="03ab0-105">Installation à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="03ab0-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="03ab0-106">Installez [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="03ab0-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="03ab0-107">**Remarque :** Installation 64 bits requise.</span><span class="sxs-lookup"><span data-stu-id="03ab0-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="03ab0-108">Ouvrez une invite Anaconda.</span><span class="sxs-lookup"><span data-stu-id="03ab0-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="03ab0-109">Si vous préférez utiliser PowerShell ou pwsh : ouvrez un interpréteur de commandes, exécutez `conda init powershell`, puis fermez et rouvrez l’interpréteur</span><span class="sxs-lookup"><span data-stu-id="03ab0-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="03ab0-110">Créez puis activez un nouvel environnement conda nommé `qsharp-env` avec les packages nécessaires (y compris Jupyter Notebook et IQ#) en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="03ab0-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="03ab0-111">Exécutez `python -c "import qsharp"` à partir du même terminal pour vérifier votre installation et ajouter à votre cache de package local tous les composants QDK nécessaires.</span><span class="sxs-lookup"><span data-stu-id="03ab0-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="03ab0-112">Installation à l’aide de l’interface CLI .NET et de pip (avancé)</span><span class="sxs-lookup"><span data-stu-id="03ab0-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="03ab0-113">Configuration requise :</span><span class="sxs-lookup"><span data-stu-id="03ab0-113">Prerequisites:</span></span>

    - <span data-ttu-id="03ab0-114">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="03ab0-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="03ab0-115">Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="03ab0-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="03ab0-116">Kit SDK .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="03ab0-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="03ab0-117">Installez le package `qsharp`, un package Python qui assure l’interopérabilité entre Q# et Python.</span><span class="sxs-lookup"><span data-stu-id="03ab0-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="03ab0-118">Installez IQ#, un noyau utilisé par Jupyter et Python qui offre les fonctionnalités de base nécessaires à la compilation et à l’exécution d’opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="03ab0-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="03ab0-119">Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.</span><span class="sxs-lookup"><span data-stu-id="03ab0-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="03ab0-120">Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="03ab0-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="03ab0-121">où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="03ab0-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="03ab0-122">En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="03ab0-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="03ab0-123">Et voilà !</span><span class="sxs-lookup"><span data-stu-id="03ab0-123">That's it!</span></span> <span data-ttu-id="03ab0-124">Vous disposez maintenant du package Python `qsharp` et du noyau IQ# pour Jupyter, qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q# à partir de Python et vous permet d’utiliser les notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="03ab0-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="03ab0-125">Choisir votre IDE</span><span class="sxs-lookup"><span data-stu-id="03ab0-125">Choose your IDE</span></span>

<span data-ttu-id="03ab0-126">Bien que vous puissiez utiliser Q# avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="03ab0-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="03ab0-127">L’extension Visual Studio Code QDK vous permet de tirer parti de fonctionnalités plus riches, telles que les avertissements, la coloration syntaxique, les modèles de projets, etc.</span><span class="sxs-lookup"><span data-stu-id="03ab0-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="03ab0-128">Si vous souhaitez utiliser VS Code :</span><span class="sxs-lookup"><span data-stu-id="03ab0-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="03ab0-129">Installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).</span><span class="sxs-lookup"><span data-stu-id="03ab0-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="03ab0-130">Installez l’[extension QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="03ab0-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="03ab0-131">Si vous souhaitez utiliser un autre éditeur, les instructions ci-dessus vous indiqueront tout ce que vous avez besoin de savoir.</span><span class="sxs-lookup"><span data-stu-id="03ab0-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="03ab0-132">Écrire votre premier programme Q#</span><span class="sxs-lookup"><span data-stu-id="03ab0-132">Write your first Q# program</span></span>

<span data-ttu-id="03ab0-133">Vous êtes maintenant prêt à vérifier l’installation de votre package Python `qsharp` en écrivant et en exécutant un programme Q# simple.</span><span class="sxs-lookup"><span data-stu-id="03ab0-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="03ab0-134">Créez une opération Q# minimale en créant un fichier appelé `Operation.qs` et en y ajoutant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="03ab0-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="03ab0-135">Dans le même dossier que `Operation.qs`, créez un programme Python appelé `host.py` pour simuler l’opération Q# `SampleQuantumRandomNumberGenerator()` :</span><span class="sxs-lookup"><span data-stu-id="03ab0-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="03ab0-136">À partir de l’environnement que vous avez créé lors de l’installation (c’est-à-dire, l’environnement conda ou l’environnement Python dans lequel vous avez installé `qsharp`), exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="03ab0-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="03ab0-137">Vous devez voir le résultat de l’opération que vous avez appelée.</span><span class="sxs-lookup"><span data-stu-id="03ab0-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="03ab0-138">Dans ce cas, étant donné que votre opération génère un résultat aléatoire, vous verrez soit `0`, soit `1` à l’écran.</span><span class="sxs-lookup"><span data-stu-id="03ab0-138">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="03ab0-139">Si vous exécutez le programme à plusieurs reprises, vous devriez voir chaque résultat environ une fois sur deux.</span><span class="sxs-lookup"><span data-stu-id="03ab0-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="03ab0-140">Le code Python est un programme Python normal.</span><span class="sxs-lookup"><span data-stu-id="03ab0-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="03ab0-141">Pour écrire le programme Python et appeler les opérations Q#, vous pouvez utiliser n’importe quel environnement Python, y compris les notebooks Jupyter basés sur Python.</span><span class="sxs-lookup"><span data-stu-id="03ab0-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="03ab0-142">Le programme Python peut importer des opérations Q# à partir de n’importe quel fichier .qs situé dans le même dossier que le code Python.</span><span class="sxs-lookup"><span data-stu-id="03ab0-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03ab0-143">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="03ab0-143">Next steps</span></span>

<span data-ttu-id="03ab0-144">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez suivre ce tutoriel en vue d’écrire et d’exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="03ab0-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
