---
title: Concevoir votre propre classifieur avec QDK
description: Découvrez les concepts de base de la conception de modèles de circuits pour le classifieur de circuit quantique.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630243"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="f2a90-103">Concevoir votre propre classifieur</span><span class="sxs-lookup"><span data-stu-id="f2a90-103">Design your own classifier</span></span>

<span data-ttu-id="f2a90-104">Dans ce guide, vous allez découvrir les concepts de base qui sous-tendent la conception de modèles de circuit pour le classifieur d’un circuit orienté Quantum.</span><span class="sxs-lookup"><span data-stu-id="f2a90-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="f2a90-105">Comme dans l’apprentissage profond classique, il n’existe aucune règle générale pour choisir une architecture spécifique.</span><span class="sxs-lookup"><span data-stu-id="f2a90-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="f2a90-106">Selon le problème, certaines architectures fonctionnent mieux que d’autres.</span><span class="sxs-lookup"><span data-stu-id="f2a90-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="f2a90-107">Toutefois, certains concepts peuvent être utiles lors de la conception du circuit :</span><span class="sxs-lookup"><span data-stu-id="f2a90-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="f2a90-108">Un grand nombre de paramètres implique un modèle plus flexible, qui peut être adapté à la création de limites de classification compliquées, mais qui peuvent également être plus susceptibles d’être surajustés.</span><span class="sxs-lookup"><span data-stu-id="f2a90-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="f2a90-109">La contangation des portes entre les qubits est essentielle pour capturer les corrélations entre les fonctionnalités de Quantum.</span><span class="sxs-lookup"><span data-stu-id="f2a90-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="f2a90-110">Comment créer un classifieur avec Q\#</span><span class="sxs-lookup"><span data-stu-id="f2a90-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="f2a90-111">Pour créer un classifieur, nous allons concaténer des rotations contrôlées par paramétrée dans notre modèle de circuit.</span><span class="sxs-lookup"><span data-stu-id="f2a90-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="f2a90-112">Pour ce faire, nous pouvons utiliser le type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) défini dans la bibliothèque de machine learning Quantum.</span><span class="sxs-lookup"><span data-stu-id="f2a90-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="f2a90-113">Ce type accepte quatre arguments qui déterminent : l’index du qubit cible, le tableau des index du qubits de contrôle, l’axe de rotation et l’index du paramètre associé dans le tableau des paramètres définissant le modèle.</span><span class="sxs-lookup"><span data-stu-id="f2a90-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="f2a90-114">Voyons un exemple de classifieur.</span><span class="sxs-lookup"><span data-stu-id="f2a90-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="f2a90-115">Dans l' [exemple de demi-lunes](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), nous pouvons trouver le classifieur suivant défini dans le fichier `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="f2a90-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="f2a90-116">Nous définissons ici une fonction qui retourne un tableau d' `ControlledRotation` éléments, ainsi qu’un tableau de paramètres et un biais définit notre [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) .</span><span class="sxs-lookup"><span data-stu-id="f2a90-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="f2a90-117">Ce type est fondamental dans la bibliothèque de Machine Learning Quantum et définit le classifieur.</span><span class="sxs-lookup"><span data-stu-id="f2a90-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="f2a90-118">Le circuit défini dans la fonction ci-dessus fait partie d’un classifieur dans lequel chaque échantillon du jeu de données contient deux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="f2a90-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="f2a90-119">Par conséquent, nous avons uniquement besoin de deux qubits.</span><span class="sxs-lookup"><span data-stu-id="f2a90-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="f2a90-120">La représentation graphique du circuit est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f2a90-120">The graphical representation of the circuit is:</span></span>

 ![Exemple de modèle de circuit](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="f2a90-122">Utiliser les fonctions de bibliothèque pour écrire des couches de portes</span><span class="sxs-lookup"><span data-stu-id="f2a90-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="f2a90-123">Supposons que nous disposons d’un jeu de données avec 784 fonctionnalités par instance, par exemple des images de 28 × 28 pixels, comme le jeu de données MNIST.</span><span class="sxs-lookup"><span data-stu-id="f2a90-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="f2a90-124">Dans ce cas, la largeur du circuit est suffisamment grande pour permettre l’écriture à la main chaque porte individuelle devient une tâche possible mais difficile.</span><span class="sxs-lookup"><span data-stu-id="f2a90-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="f2a90-125">C’est pourquoi la bibliothèque Quantum Machine Learning fournit un ensemble d’outils permettant de générer automatiquement des couches de rotations paramétrée.</span><span class="sxs-lookup"><span data-stu-id="f2a90-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="f2a90-126">Par exemple, la fonction [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) retourne un tableau de rotations uniqubit non contrôlées sur un axe donné, avec une rotation pour chaque qubit du Registre, chaque paramétrée par un paramètre de modèle différent.</span><span class="sxs-lookup"><span data-stu-id="f2a90-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="f2a90-127">Par exemple, `LocalRotationsLayer(4, X)` retourne le jeu de portes suivant :</span><span class="sxs-lookup"><span data-stu-id="f2a90-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Couche de rotations locales](~/media/local_rotations_layer.PNG)

<span data-ttu-id="f2a90-129">Nous vous recommandons d’explorer les informations [de référence sur l’API de la bibliothèque de machine learning Quantum](xref:microsoft.quantum.machinelearning) pour découvrir tous les outils disponibles pour rationaliser la conception du circuit.</span><span class="sxs-lookup"><span data-stu-id="f2a90-129">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2a90-130">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f2a90-130">Next steps</span></span>

 <span data-ttu-id="f2a90-131">Essayez différentes structures dans les exemples fournis par les exemples.</span><span class="sxs-lookup"><span data-stu-id="f2a90-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="f2a90-132">Des modifications ont-elles été apportées aux performances du modèle ?</span><span class="sxs-lookup"><span data-stu-id="f2a90-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="f2a90-133">Dans le didacticiel suivant, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) , vous apprendrez à charger des jeux de données pour essayer d’explorer de nouvelles architectures de classifieurs.</span><span class="sxs-lookup"><span data-stu-id="f2a90-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
