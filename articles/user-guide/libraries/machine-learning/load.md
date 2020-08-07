---
title: Chargement de données classiques
description: Découvrez comment charger votre propre jeu de données pour former un modèle de classifieur avec l’Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868829"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="7665f-103">Charger et classer vos propres jeux de données</span><span class="sxs-lookup"><span data-stu-id="7665f-103">Load and classify your own datasets</span></span>

<span data-ttu-id="7665f-104">Dans ce bref didacticiel, nous allons apprendre à charger votre propre jeu de données pour former un modèle de classifieur avec le kit de développement quantique (QDK).</span><span class="sxs-lookup"><span data-stu-id="7665f-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="7665f-105">Nous vous recommandons vivement d’utiliser un format de sérialisation standardisé, tel que les [fichiers JSON](https://en.wikipedia.org/wiki/JSON) , pour stocker vos données.</span><span class="sxs-lookup"><span data-stu-id="7665f-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="7665f-106">Ces formats offrent une haute compatibilité avec différents frameworks comme Python et l’écosystème .NET.</span><span class="sxs-lookup"><span data-stu-id="7665f-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="7665f-107">En particulier, nous vous recommandons d’utiliser notre modèle pour le chargement des données, afin que vous puissiez copier-coller le code directement à partir des exemples.</span><span class="sxs-lookup"><span data-stu-id="7665f-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="7665f-108">Modèle pour le chargement de vos jeux de données</span><span class="sxs-lookup"><span data-stu-id="7665f-108">Template for loading your datasets</span></span>

<span data-ttu-id="7665f-109">Supposons que nous disposons d’un jeu de données d’apprentissage $ (x, y) $ de taille $N = $2 où chaque instance $x _i $ de $x $ a trois fonctionnalités : $x _ {I1} $, $x _ {I2} $ et $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="7665f-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="7665f-110">Le DataSet de validation a la même structure.</span><span class="sxs-lookup"><span data-stu-id="7665f-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="7665f-111">Ces jeux peuvent être représentés par un `data.json` fichier similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7665f-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="7665f-112">Exemple utilisant le modèle</span><span class="sxs-lookup"><span data-stu-id="7665f-112">Example using the template</span></span>

<span data-ttu-id="7665f-113">Supposons que nous ayons un petit jeu de données avec des hauteurs et des poids de différents chats et chiens.</span><span class="sxs-lookup"><span data-stu-id="7665f-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="7665f-114">Ce jeu de données est très petit pour effectuer l’apprentissage d’un modèle, mais il sera suffisant pour montrer le processus de chargement d’un jeu de données.</span><span class="sxs-lookup"><span data-stu-id="7665f-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="7665f-115">Hauteur (m)</span><span class="sxs-lookup"><span data-stu-id="7665f-115">Height (m)</span></span> | <span data-ttu-id="7665f-116">Poids (kg)</span><span class="sxs-lookup"><span data-stu-id="7665f-116">Weight (kg)</span></span> | <span data-ttu-id="7665f-117">Animal</span><span class="sxs-lookup"><span data-stu-id="7665f-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="7665f-118">0,54</span><span class="sxs-lookup"><span data-stu-id="7665f-118">0.54</span></span>      | <span data-ttu-id="7665f-119">30</span><span class="sxs-lookup"><span data-stu-id="7665f-119">30</span></span>         | <span data-ttu-id="7665f-120">Dog</span><span class="sxs-lookup"><span data-stu-id="7665f-120">Dog</span></span>    |
| <span data-ttu-id="7665f-121">0.30</span><span class="sxs-lookup"><span data-stu-id="7665f-121">0.30</span></span>      | <span data-ttu-id="7665f-122">8</span><span class="sxs-lookup"><span data-stu-id="7665f-122">8</span></span>          | <span data-ttu-id="7665f-123">Chats</span><span class="sxs-lookup"><span data-stu-id="7665f-123">Cat</span></span>    |
| <span data-ttu-id="7665f-124">0,91</span><span class="sxs-lookup"><span data-stu-id="7665f-124">0.91</span></span>      | <span data-ttu-id="7665f-125">44</span><span class="sxs-lookup"><span data-stu-id="7665f-125">44</span></span>         | <span data-ttu-id="7665f-126">Dog</span><span class="sxs-lookup"><span data-stu-id="7665f-126">Dog</span></span>    |
| <span data-ttu-id="7665f-127">0.86</span><span class="sxs-lookup"><span data-stu-id="7665f-127">0.86</span></span>      | <span data-ttu-id="7665f-128">31</span><span class="sxs-lookup"><span data-stu-id="7665f-128">31</span></span>          | <span data-ttu-id="7665f-129">Dog</span><span class="sxs-lookup"><span data-stu-id="7665f-129">Dog</span></span>    |
| <span data-ttu-id="7665f-130">0.32</span><span class="sxs-lookup"><span data-stu-id="7665f-130">0.32</span></span>      | <span data-ttu-id="7665f-131">5</span><span class="sxs-lookup"><span data-stu-id="7665f-131">5</span></span>         | <span data-ttu-id="7665f-132">Chats</span><span class="sxs-lookup"><span data-stu-id="7665f-132">Cat</span></span>    |
| <span data-ttu-id="7665f-133">0,25</span><span class="sxs-lookup"><span data-stu-id="7665f-133">0.25</span></span>      | <span data-ttu-id="7665f-134">4</span><span class="sxs-lookup"><span data-stu-id="7665f-134">4</span></span>          | <span data-ttu-id="7665f-135">Chats</span><span class="sxs-lookup"><span data-stu-id="7665f-135">Cat</span></span>    |

<span data-ttu-id="7665f-136">Le processus est le suivant :</span><span class="sxs-lookup"><span data-stu-id="7665f-136">The process is:</span></span>

- <span data-ttu-id="7665f-137">Tout d’abord, nous devons séparer le jeu de données en formation et validation.</span><span class="sxs-lookup"><span data-stu-id="7665f-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="7665f-138">Dans ce cas, nous pouvons simplement prendre les trois premiers exemples pour la formation et le reste des exemples à des fins de validation.</span><span class="sxs-lookup"><span data-stu-id="7665f-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="7665f-139">En général, il est recommandé d’échantillonner de façon aléatoire le jeu de données de formation et de validation pour éviter les écarts indésirables dans les données d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="7665f-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="7665f-140">Deuxièmement, nous devons attribuer une étiquette numérique à chaque classe.</span><span class="sxs-lookup"><span data-stu-id="7665f-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="7665f-141">Notez que, pour le moment, la bibliothèque QML admet uniquement les problèmes de classification binaire.</span><span class="sxs-lookup"><span data-stu-id="7665f-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="7665f-142">Nous allons donc attribuer l’étiquette 0 à la classe `Dog` et le numéro 1 à la classe `Cat` .</span><span class="sxs-lookup"><span data-stu-id="7665f-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="7665f-143">Enfin, nous remplissons le modèle à l’aide des données de notre jeu de données.</span><span class="sxs-lookup"><span data-stu-id="7665f-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="7665f-144">Notez que pour les jeux de données volumineux, vous devez générer un petit script pour générer automatiquement le modèle à partir de votre jeu de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="7665f-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="7665f-145">Ce script dépend du format d’origine de votre jeu de données.</span><span class="sxs-lookup"><span data-stu-id="7665f-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="7665f-146">Pour notre jeu de données, le `data.json` fichier est :</span><span class="sxs-lookup"><span data-stu-id="7665f-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="7665f-147">Chargement des données</span><span class="sxs-lookup"><span data-stu-id="7665f-147">Loading the data</span></span>

<span data-ttu-id="7665f-148">Une fois que vos données sont sérialisées sous la forme d’un fichier JSON, vous pouvez les charger dans à l’aide des bibliothèques JSON fournies avec le langage hôte de votre choix.</span><span class="sxs-lookup"><span data-stu-id="7665f-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="7665f-149">Python</span><span class="sxs-lookup"><span data-stu-id="7665f-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="7665f-150">Python fournit le [ `json` package intégré](https://docs.python.org/3.7/library/json.html) pour l’utilisation de données sérialisées JSON :</span><span class="sxs-lookup"><span data-stu-id="7665f-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="7665f-151">C#</span><span class="sxs-lookup"><span data-stu-id="7665f-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="7665f-152">La plateforme .NET Core fournit le [ `System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) pour l’utilisation de données sérialisées JSON :</span><span class="sxs-lookup"><span data-stu-id="7665f-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="7665f-153">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="7665f-153">Next steps</span></span>

<span data-ttu-id="7665f-154">Vous êtes maintenant prêt à commencer à exécuter vos propres expériences avec vos propres jeux de données.</span><span class="sxs-lookup"><span data-stu-id="7665f-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="7665f-155">Essayez différents classifieurs et jeux de données et contribuez à la communauté partageant vos résultats.</span><span class="sxs-lookup"><span data-stu-id="7665f-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
