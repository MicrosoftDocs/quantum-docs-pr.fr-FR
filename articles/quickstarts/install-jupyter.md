---
title: Développer avec des notebooks Jupyter Q#
description: Découvrez comment créer une application Q# à l’aide de Jupyter Notebook.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: b34d89ab33a4644c1dd4342949685f9bf84babd8
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771402"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="bc01e-103">Développer avec des notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="bc01e-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="bc01e-104">Installez le QDK pour le développement d’opérations Q# sur des notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="bc01e-105">Les notebooks Jupyter permettent l’exécution de code sur place avec les instructions, les notes et autre contenu.</span><span class="sxs-lookup"><span data-stu-id="bc01e-105">Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content.</span></span> <span data-ttu-id="bc01e-106">Cet environnement est idéal pour écrire du code Q# avec des explications incorporées ou des tutoriels interactifs sur l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="bc01e-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="bc01e-107">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="bc01e-108">Installer le noyau Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="bc01e-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="bc01e-109">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="bc01e-110">Installation à l’aide de conda (recommandé)</span><span class="sxs-lookup"><span data-stu-id="bc01e-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="bc01e-111">Installez [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="bc01e-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="bc01e-112">**Remarque :** Installation 64 bits requise.</span><span class="sxs-lookup"><span data-stu-id="bc01e-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="bc01e-113">Ouvrez une invite Anaconda.</span><span class="sxs-lookup"><span data-stu-id="bc01e-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="bc01e-114">Si vous préférez utiliser PowerShell ou pwsh : ouvrez un interpréteur de commandes, exécutez `conda init powershell`, puis fermez et rouvrez l’interpréteur</span><span class="sxs-lookup"><span data-stu-id="bc01e-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="bc01e-115">Créez puis activez un nouvel environnement conda nommé `qsharp-env` avec les packages nécessaires (y compris Jupyter Notebook et IQ#) en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc01e-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="bc01e-116">Exécutez `python -c "import qsharp"` à partir du même terminal pour vérifier votre installation et ajouter à votre cache de package local tous les composants QDK nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bc01e-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="bc01e-117">Installation à l’aide de l’interface CLI .NET (avancé)</span><span class="sxs-lookup"><span data-stu-id="bc01e-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="bc01e-118">Configuration requise :</span><span class="sxs-lookup"><span data-stu-id="bc01e-118">Prerequisites:</span></span>

    - <span data-ttu-id="bc01e-119">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="bc01e-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="bc01e-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="bc01e-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="bc01e-121">Kit SDK .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="bc01e-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="bc01e-122">Installez le package `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="bc01e-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="bc01e-123">Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.</span><span class="sxs-lookup"><span data-stu-id="bc01e-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="bc01e-124">Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bc01e-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="bc01e-125">où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bc01e-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="bc01e-126">En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bc01e-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="bc01e-127">Et voilà !</span><span class="sxs-lookup"><span data-stu-id="bc01e-127">That's it!</span></span> <span data-ttu-id="bc01e-128">Vous disposez maintenant du noyau IQ# pour Jupyter, qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q# à partir des notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="bc01e-129">Créer votre premier notebook Q#</span><span class="sxs-lookup"><span data-stu-id="bc01e-129">Create your first Q# notebook</span></span>

<span data-ttu-id="bc01e-130">Vous êtes maintenant prêt à vérifier l’installation de Jupyter Notebook Q# en écrivant et en exécutant une simple opération Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="bc01e-131">À partir de l’environnement que vous avez créé lors de l’installation (c’est-à-dire, soit l’environnement conda que vous avez créé, soit l’environnement Python dans lequel vous avez installé Jupyter), exécutez la commande suivante pour démarrer le serveur Jupyter Notebook :</span><span class="sxs-lookup"><span data-stu-id="bc01e-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="bc01e-132">Si le notebook Jupyter ne s’ouvre pas automatiquement dans votre navigateur, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="bc01e-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="bc01e-133">Choisissez **Nouveau → Q#** pour créer un Jupyter Notebook avec un noyau Q#, puis ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="bc01e-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="bc01e-134">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="bc01e-134">Run this cell of the notebook:</span></span>

    ![Cellule de Jupyter Notebook avec code Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="bc01e-136">Vous devriez voir `SampleQuantumRandomNumberGenerator` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="bc01e-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="bc01e-137">Lorsqu’il est exécuté dans Jupyter Notebook, le code Q# est compilé et la cellule affiche le nom des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="bc01e-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="bc01e-138">Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="bc01e-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="bc01e-140">Vous devez voir le résultat de l’opération que vous avez appelée.</span><span class="sxs-lookup"><span data-stu-id="bc01e-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="bc01e-141">Dans ce cas, étant donné que votre opération génère un résultat aléatoire, vous verrez soit `Zero`, soit `One` à l’écran.</span><span class="sxs-lookup"><span data-stu-id="bc01e-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="bc01e-142">Si vous exécutez la cellule à plusieurs reprises, vous devriez voir chaque résultat environ une fois sur deux.</span><span class="sxs-lookup"><span data-stu-id="bc01e-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc01e-143">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="bc01e-143">Next steps</span></span>

<span data-ttu-id="bc01e-144">Maintenant que vous avez installé le QDK pour les notebooks Jupyter Q#, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng) en écrivant du code Q# directement dans l’environnement Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="bc01e-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="bc01e-145">Pour obtenir plus d’exemples de ce que vous pouvez faire avec des notebooks Jupyter Q#, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc01e-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="bc01e-146">[Présentation de Q# et de Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)</span><span class="sxs-lookup"><span data-stu-id="bc01e-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="bc01e-147">Vous y trouverez un notebook Jupyter Q# qui montre en détail comment utiliser du code Q# dans l’environnement Jupyter.</span><span class="sxs-lookup"><span data-stu-id="bc01e-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="bc01e-148">[Katas Quantum](xref:microsoft.quantum.overview.katas), une collection open source de tutoriels auto-rythmés et d’exercices de programmation sous la forme de notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="bc01e-149">Les [notebooks des katas Quantum](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ.</span><span class="sxs-lookup"><span data-stu-id="bc01e-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="bc01e-150">Les katas Quantum sont conçus pour vous inculquer des notions de l’informatique quantique et de la programmation en Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="bc01e-151">Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="bc01e-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
