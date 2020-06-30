---
title: Développer avec des notebooks Jupyter Q#
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274096"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="fae62-102">Développer avec des notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="fae62-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="fae62-103">Installez le QDK pour le développement d’opérations Q# sur des notebooks Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="fae62-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="fae62-104">Les notebooks Jupyter permettent l’exécution de code sur place aux côtés d’instructions, de notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="fae62-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="fae62-105">Cet environnement est idéal pour écrire du code Q# avec des explications incorporées ou des tutoriels interactifs sur l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="fae62-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="fae62-106">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="fae62-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="fae62-107">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="fae62-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="fae62-108">Dans les notebooks Jupyter Q#, vous pouvez uniquement exécuter du code Q# et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, des fichiers Python ou C#).</span><span class="sxs-lookup"><span data-stu-id="fae62-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="fae62-109">Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme quantique.</span><span class="sxs-lookup"><span data-stu-id="fae62-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="fae62-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fae62-110">Prerequisites</span></span>

    - <span data-ttu-id="fae62-111">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="fae62-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="fae62-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="fae62-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="fae62-113">Kit SDK .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fae62-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="fae62-114">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="fae62-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="fae62-115">Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.</span><span class="sxs-lookup"><span data-stu-id="fae62-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="fae62-116">Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fae62-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="fae62-117">où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fae62-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="fae62-118">En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fae62-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="fae62-119">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="fae62-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="fae62-120">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="fae62-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="fae62-121">Pour ouvrir le notebook Jupyter, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="fae62-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="fae62-122">Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="fae62-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="fae62-123">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="fae62-123">Run this cell of the notebook:</span></span>

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="fae62-125">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="fae62-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="fae62-126">Lors de l’exécution dans un notebook Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="fae62-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="fae62-127">Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="fae62-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="fae62-129">Le message doit s’afficher à l’écran ainsi que le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` car notre opération retourne simplement un type `Unit`).</span><span class="sxs-lookup"><span data-stu-id="fae62-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fae62-130">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fae62-130">Next steps</span></span>

<span data-ttu-id="fae62-131">Une fois le QDK installé pour les notebooks Jupyter Q#, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng) en écrivant votre code Q# directement dans l’environnement Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="fae62-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="fae62-132">Pour obtenir plus d’exemples de ce que vous pouvez faire avec des notebooks Jupyter Q#, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fae62-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="fae62-133">[Présentation de Q# et de Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)</span><span class="sxs-lookup"><span data-stu-id="fae62-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="fae62-134">Vous trouverez ici un notebook Jupyter Q# qui montre comment utiliser Q# dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="fae62-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="fae62-135">[Katas Quantum](xref:microsoft.quantum.overview.katas), une collection open source de tutoriels auto-rythmés et d’exercices de programmation sous la forme de notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="fae62-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="fae62-136">Les [notebooks des katas Quantum](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ.</span><span class="sxs-lookup"><span data-stu-id="fae62-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="fae62-137">Les katas Quantum sont conçus pour vous inculquer des notions de l’informatique quantique et de la programmation en Q#.</span><span class="sxs-lookup"><span data-stu-id="fae62-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="fae62-138">Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="fae62-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
