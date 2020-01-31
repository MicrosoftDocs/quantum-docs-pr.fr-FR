---
title: 'Développer avec des blocs-notes Jupyter Q #'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831067"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="e0cd2-102">Développer avec des blocs-notes Jupyter Q #</span><span class="sxs-lookup"><span data-stu-id="e0cd2-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="e0cd2-103">Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="e0cd2-104">Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="e0cd2-105">Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="e0cd2-106">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="e0cd2-107">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="e0cd2-108">Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir C# de programmes hôtes externes (par exemple, Python ou fichiers).</span><span class="sxs-lookup"><span data-stu-id="e0cd2-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="e0cd2-109">Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="e0cd2-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e0cd2-110">Pre-requisites</span></span>

    - <span data-ttu-id="e0cd2-111">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e0cd2-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="e0cd2-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="e0cd2-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="e0cd2-113">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="e0cd2-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="e0cd2-114">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e0cd2-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="e0cd2-115">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="e0cd2-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e0cd2-116">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="e0cd2-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="e0cd2-117">Pour ouvrir le bloc-notes Jupyter, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="e0cd2-118">Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="e0cd2-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="e0cd2-119">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="e0cd2-119">Run this cell of the notebook:</span></span>

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="e0cd2-121">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="e0cd2-122">Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="e0cd2-123">Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="e0cd2-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="e0cd2-125">Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` parce que notre opération retourne simplement un type de `Unit`).</span><span class="sxs-lookup"><span data-stu-id="e0cd2-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="e0cd2-126">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="e0cd2-126">What's next?</span></span>

<span data-ttu-id="e0cd2-127">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="e0cd2-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
