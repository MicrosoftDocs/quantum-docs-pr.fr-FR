---
title: Classification de base avec la bibliothèque de Machine Learning Quantum
description: Découvrez comment exécuter un classificateur séquentiel Quantum écrit dans Q# à l’aide de la bibliothèque quantum machine learning de Microsoft QDK.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fe686a87fbdc610badc0bbcbc0bf7b065e0bce9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854043"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="55583-103">Classification de base : classer les données avec QDK</span><span class="sxs-lookup"><span data-stu-id="55583-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="55583-104">Dans ce guide de démarrage rapide, vous allez apprendre à exécuter un classificateur séquentiel Quantum écrit dans Q# à l’aide de la bibliothèque quantum machine learning de QDK.</span><span class="sxs-lookup"><span data-stu-id="55583-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="55583-105">Dans ce guide, nous allons utiliser le jeu de données de la demi-lune, à l’aide d’une structure de classifieur définie dans Q# .</span><span class="sxs-lookup"><span data-stu-id="55583-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55583-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="55583-106">Prerequisites</span></span>

- <span data-ttu-id="55583-107">Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="55583-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="55583-108">Créez un Q# projet pour un [programme hôte python](xref:microsoft.quantum.install.python) ou un [programme hôte C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="55583-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="55583-109">Programme hôte</span><span class="sxs-lookup"><span data-stu-id="55583-109">Host program</span></span>

<span data-ttu-id="55583-110">Votre programme hôte se compose de trois parties :</span><span class="sxs-lookup"><span data-stu-id="55583-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="55583-111">Chargez le jeu de données et choisissez un ensemble de paramètres de démarrage pour votre modèle.</span><span class="sxs-lookup"><span data-stu-id="55583-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="55583-112">Exécutez la formation pour déterminer les paramètres et l’écart du modèle.</span><span class="sxs-lookup"><span data-stu-id="55583-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="55583-113">Valider le modèle pour déterminer sa précision</span><span class="sxs-lookup"><span data-stu-id="55583-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="55583-114">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="55583-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="55583-115">Pour exécuter vous êtes le Q# classifieur de Python, enregistrez le code suivant sous `host.py` .</span><span class="sxs-lookup"><span data-stu-id="55583-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="55583-116">N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="55583-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="55583-117">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="55583-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="55583-118">C# avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="55583-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="55583-119">Pour exécuter vous êtes le Q# classifieur de C#, enregistrez le code suivant sous `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="55583-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="55583-120">N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="55583-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="55583-121">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="55583-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="55583-122">C# avec Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="55583-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="55583-123">Pour exécuter votre nouveau Q# programme à partir de C# dans Visual Studio, modifiez `Host.cs` pour inclure le code C# suivant.</span><span class="sxs-lookup"><span data-stu-id="55583-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="55583-124">N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="55583-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="55583-125">Appuyez sur F5 pour que le programme commence à s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="55583-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="55583-126">Une nouvelle fenêtre affiche les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="55583-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="55583-127">\#Code du classifieur Q</span><span class="sxs-lookup"><span data-stu-id="55583-127">Q\# classifier code</span></span>

<span data-ttu-id="55583-128">Voyons maintenant comment les opérations appelées par le programme hôte sont définies dans Q# .</span><span class="sxs-lookup"><span data-stu-id="55583-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="55583-129">Nous enregistrons le code suivant dans un fichier nommé `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="55583-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="55583-130">Les fonctions et opérations les plus importantes définies dans le code ci-dessus sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="55583-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="55583-131">`ClassifierStructure() : ControlledRotation[]` : dans cette fonction, nous définissons la structure de notre modèle de circuit en ajoutant les couches des portes contrôlées que nous considérons.</span><span class="sxs-lookup"><span data-stu-id="55583-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="55583-132">Cette étape est analogue à la déclaration des couches de neurones dans un modèle d’apprentissage profond séquentiel.</span><span class="sxs-lookup"><span data-stu-id="55583-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="55583-133">`TrainHalfMoonModel() : (Double[], Double)` : cette opération est la partie fondamentale du code et définit l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="55583-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="55583-134">Ici, nous chargeons les exemples à partir du jeu de données inclus dans la bibliothèque, nous définissons les hyper paramètres et les paramètres initiaux pour l’apprentissage et nous commençons l’apprentissage en appelant l’opération `TrainSequentialClassifier` incluse dans la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="55583-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="55583-135">Il génère les paramètres et le biais qui déterminent le classifieur.</span><span class="sxs-lookup"><span data-stu-id="55583-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="55583-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : cette opération définit le processus de validation pour évaluer le modèle.</span><span class="sxs-lookup"><span data-stu-id="55583-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="55583-137">Ici, nous chargeons les exemples pour la validation, le nombre de mesures par échantillon et la tolérance.</span><span class="sxs-lookup"><span data-stu-id="55583-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="55583-138">Il génère le nombre de déclassifications incorrectes sur le lot d’exemples choisi à des fins de validation.</span><span class="sxs-lookup"><span data-stu-id="55583-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55583-139">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="55583-139">Next steps</span></span>

<span data-ttu-id="55583-140">Tout d’abord, vous pouvez lire le code et essayer de modifier certains paramètres pour voir comment il affecte l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="55583-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="55583-141">Ensuite, dans le didacticiel suivant, [Concevez votre propre classifieur](xref:microsoft.quantum.libraries.machine-learning.design), vous apprendrez à définir la structure du classifieur.</span><span class="sxs-lookup"><span data-stu-id="55583-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
