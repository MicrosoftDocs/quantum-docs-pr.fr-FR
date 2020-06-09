---
title: Développer avec Q# + Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577818"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="67313-102">Développer avec Q# + Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="67313-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="67313-103">Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="67313-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="67313-104">Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="67313-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="67313-105">Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing.</span><span class="sxs-lookup"><span data-stu-id="67313-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="67313-106">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="67313-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="67313-107">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="67313-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="67313-108">Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, fichiers python ou C#).</span><span class="sxs-lookup"><span data-stu-id="67313-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="67313-109">Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="67313-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="67313-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="67313-110">Pre-requisites</span></span>

    - <span data-ttu-id="67313-111">[Python](https://www.python.org/downloads/) 3,6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="67313-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="67313-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="67313-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="67313-113">Kit SDK .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="67313-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="67313-114">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="67313-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="67313-115">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="67313-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="67313-116">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="67313-116">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="67313-117">Pour ouvrir la Jupyter Notebook, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="67313-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="67313-118">Créez un Jupyter Notebook avec un noyau Q #, puis ajoutez le code suivant à la première cellule du bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="67313-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="67313-119">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="67313-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook cellule avec le code Q #](~/media/install-guide-jupyter.png)

        <span data-ttu-id="67313-121">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="67313-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="67313-122">En cas d’exécution dans Jupyter Notebook, le code Q # est compilé et le bloc-notes renvoie le nom de la ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="67313-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="67313-123">Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la `%simulate` commande :</span><span class="sxs-lookup"><span data-stu-id="67313-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook cellule avec% simulateur magique](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="67313-125">Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` , car notre opération retourne simplement un `Unit` type).</span><span class="sxs-lookup"><span data-stu-id="67313-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="67313-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="67313-126">Next steps</span></span>

<span data-ttu-id="67313-127">Maintenant que vous avez installé le QDK pour les blocs-notes Q # Jupyter, vous pouvez écrire et exécuter [votre premier programme Quantum](xref:microsoft.quantum.quickstarts.qrng) en écrivant votre code Q # directement dans l’environnement de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="67313-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="67313-128">Pour obtenir plus d’exemples de ce que vous pouvez faire avec les blocs-notes Jupyter Q #, consultez :</span><span class="sxs-lookup"><span data-stu-id="67313-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="67313-129">[Introduction à Q # et Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="67313-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="67313-130">Vous y trouverez une Jupyter Notebook Q # qui montre comment utiliser Q # dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="67313-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="67313-131">[Quantum katas](xref:microsoft.quantum.overview.katas), une collection Open source de didacticiels à votre rythme et de jeux d’exercices de programmation sous la forme de blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="67313-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="67313-132">Les [blocs-notes Quantum katas Tutorial](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ.</span><span class="sxs-lookup"><span data-stu-id="67313-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="67313-133">Les katas Quantum visent à vous enseigner des éléments de quantum computing et Q # Programming en même temps.</span><span class="sxs-lookup"><span data-stu-id="67313-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="67313-134">Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="67313-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
