---
title: Classification de base avec la bibliothèque de Machine Learning Quantum
description: 'Découvrez comment exécuter un classifieur séquentiel Quantum écrit en Q # à l’aide de la bibliothèque Quantum Machine Learning de Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: ddd889fdfabb505d7118c1eff551a6fbfa757309
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327643"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="aa2e4-103">Classification de base : classer les données avec QDK</span><span class="sxs-lookup"><span data-stu-id="aa2e4-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="aa2e4-104">Dans ce guide de démarrage rapide, vous allez apprendre à exécuter un classifieur séquentiel Quantum écrit en Q # à l’aide de la bibliothèque Quantum Machine Learning de QDK.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="aa2e4-105">Dans ce guide, nous allons utiliser le jeu de données de la demi-lune, à l’aide d’une structure de classifieur définie dans Q #.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa2e4-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="aa2e4-106">Prerequisites</span></span>

- <span data-ttu-id="aa2e4-107">Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="aa2e4-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="aa2e4-108">Créez un projet Q # pour un [programme hôte python](xref:microsoft.quantum.install.python) ou un [programme hôte C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="aa2e4-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="aa2e4-109">Programme hôte</span><span class="sxs-lookup"><span data-stu-id="aa2e4-109">Host program</span></span>

<span data-ttu-id="aa2e4-110">Votre programme hôte se compose de trois parties :</span><span class="sxs-lookup"><span data-stu-id="aa2e4-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="aa2e4-111">Chargez le jeu de données et choisissez un ensemble de paramètres de démarrage pour votre modèle.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="aa2e4-112">Exécutez la formation pour déterminer les paramètres et l’écart du modèle.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="aa2e4-113">Valider le modèle pour déterminer sa précision</span><span class="sxs-lookup"><span data-stu-id="aa2e4-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="aa2e4-114">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="aa2e4-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="aa2e4-115">Pour exécuter vous êtes le classificateur Q # de Python, enregistrez le code suivant sous `host.py` .</span><span class="sxs-lookup"><span data-stu-id="aa2e4-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="aa2e4-116">N’oubliez pas que vous avez également besoin du fichier Q # `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="aa2e4-117">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="aa2e4-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="aa2e4-118">C# avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="aa2e4-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="aa2e4-119">Pour exécuter vous êtes le classificateur Q # à partir de C#, enregistrez le code suivant sous `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="aa2e4-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="aa2e4-120">N’oubliez pas que vous avez également besoin du fichier Q # `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="aa2e4-121">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="aa2e4-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="aa2e4-122">C# avec Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="aa2e4-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="aa2e4-123">Pour exécuter votre nouveau programme Q # à partir de C# dans Visual Studio, modifiez `Host.cs` pour inclure le code C# suivant.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="aa2e4-124">N’oubliez pas que vous avez également besoin du fichier Q # `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="aa2e4-125">Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="aa2e4-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="aa2e4-126">\#Code du classifieur Q</span><span class="sxs-lookup"><span data-stu-id="aa2e4-126">Q\# classifier code</span></span>

<span data-ttu-id="aa2e4-127">Voyons maintenant comment les opérations appelées par le programme hôte sont définies dans Q #.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="aa2e4-128">Nous enregistrons le code suivant dans un fichier nommé `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="aa2e4-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="aa2e4-129">Les fonctions et opérations les plus importantes définies dans le code ci-dessus sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aa2e4-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="aa2e4-130">`ClassifierStructure() : ControlledRotation[]`: dans cette fonction, nous définissons la structure de notre modèle de circuit en ajoutant les couches des portes contrôlées que nous considérons.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="aa2e4-131">Cette étape est analogue à la déclaration des couches de neurones dans un modèle d’apprentissage profond séquentiel.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="aa2e4-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: cette opération est la partie fondamentale du code et définit l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="aa2e4-133">Ici, nous chargeons les exemples à partir du jeu de données inclus dans la bibliothèque, nous définissons les hyper paramètres et les paramètres initiaux pour l’apprentissage et nous commençons l’apprentissage en appelant l’opération `TrainSequentialClassifier` incluse dans la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="aa2e4-134">Il génère les paramètres et le biais qui déterminent le classifieur.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="aa2e4-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: cette opération définit le processus de validation pour évaluer le modèle.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="aa2e4-136">Ici, nous chargeons les exemples pour la validation, le nombre de mesures par échantillon et la tolérance.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="aa2e4-137">Il génère le nombre de déclassifications incorrectes sur le lot d’exemples choisi à des fins de validation.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa2e4-138">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="aa2e4-138">Next steps</span></span>

<span data-ttu-id="aa2e4-139">Tout d’abord, vous pouvez lire le code et essayer de modifier certains paramètres pour voir comment il affecte l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="aa2e4-140">Ensuite, dans le didacticiel suivant, [Concevez votre propre classifieur](xref:microsoft.quantum.libraries.machine-learning.design), vous apprendrez à définir la structure du classifieur.</span><span class="sxs-lookup"><span data-stu-id="aa2e4-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
