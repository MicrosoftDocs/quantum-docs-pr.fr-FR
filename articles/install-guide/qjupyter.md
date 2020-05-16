---
title: 'Développer avec des blocs-notes Jupyter Q #'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 38db14ccc5f2406043ff4baee3f562385cdf47a8
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426375"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="da2ac-102">Développer avec des blocs-notes Jupyter Q #</span><span class="sxs-lookup"><span data-stu-id="da2ac-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="da2ac-103">Installez le QDK pour le développement d’opérations Q # sur les blocs-notes Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="da2ac-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="da2ac-104">Les blocs-notes Jupyter autorisent l’exécution de code en place à côté des instructions, des notes et d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="da2ac-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="da2ac-105">Cet environnement est idéal pour écrire du code Q # avec des explications incorporées ou des didacticiels interactifs quantum computing.</span><span class="sxs-lookup"><span data-stu-id="da2ac-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="da2ac-106">Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.</span><span class="sxs-lookup"><span data-stu-id="da2ac-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="da2ac-107">IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="da2ac-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="da2ac-108">Dans les blocs-notes Q # Jupyter, vous pouvez uniquement exécuter le code Q #, et les opérations ne peuvent pas être appelées à partir de programmes hôtes externes (par exemple, fichiers python ou C#).</span><span class="sxs-lookup"><span data-stu-id="da2ac-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="da2ac-109">Cet environnement n’est pas approprié si votre objectif est de combiner un programme hôte classique externe avec le programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="da2ac-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="da2ac-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="da2ac-110">Pre-requisites</span></span>

    - <span data-ttu-id="da2ac-111">[Python](https://www.python.org/downloads/) 3,6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="da2ac-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="da2ac-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="da2ac-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="da2ac-113">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="da2ac-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="da2ac-114">Installez le package `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="da2ac-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="da2ac-115">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="da2ac-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="da2ac-116">Exécutez la commande suivante pour démarrer le serveur notebook :</span><span class="sxs-lookup"><span data-stu-id="da2ac-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="da2ac-117">Pour ouvrir le bloc-notes Jupyter, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="da2ac-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="da2ac-118">Créez un notebook Jupyter avec un noyau Q# et ajoutez le code suivant à la première cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="da2ac-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="da2ac-119">Exécutez cette cellule du notebook :</span><span class="sxs-lookup"><span data-stu-id="da2ac-119">Run this cell of the notebook:</span></span>

        ![Cellule de notebook Jupyter avec code Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="da2ac-121">Vous devriez voir `SayHello` dans la sortie de la cellule.</span><span class="sxs-lookup"><span data-stu-id="da2ac-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="da2ac-122">Lors de l’exécution dans des notebooks Jupyter, le code Q# est compilé et le notebook affiche le nom de l’opération ou des opérations qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="da2ac-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="da2ac-123">Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la `%simulate` commande :</span><span class="sxs-lookup"><span data-stu-id="da2ac-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="da2ac-125">Vous devez voir le message imprimé à l’écran avec le résultat de l’opération que vous avez appelée (ici, nous voyons le tuple vide `()` , car notre opération retourne simplement un `Unit` type).</span><span class="sxs-lookup"><span data-stu-id="da2ac-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="da2ac-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="da2ac-126">Next steps</span></span>

<span data-ttu-id="da2ac-127">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="da2ac-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
