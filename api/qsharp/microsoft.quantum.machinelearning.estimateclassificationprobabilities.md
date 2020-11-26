---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Opération EstimateClassificationProbabilities
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211897"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="e5960-102">Opération EstimateClassificationProbabilities</span><span class="sxs-lookup"><span data-stu-id="e5960-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="e5960-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e5960-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e5960-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e5960-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e5960-105">Étant donné un ensemble d’exemples et un classifieur séquentiel, évalue la probabilité de classification pour ces exemples en mesurant de manière répétée la sortie du classifieur sur chaque échantillon.</span><span class="sxs-lookup"><span data-stu-id="e5960-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="e5960-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e5960-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="e5960-107">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5960-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5960-108">Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="e5960-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="e5960-109">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="e5960-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="e5960-110">Modèle séquentiel à utiliser pour estimer les probabilités de classification pour les exemples donnés.</span><span class="sxs-lookup"><span data-stu-id="e5960-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="e5960-111">exemples : [double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="e5960-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="e5960-112">Tableau de vecteurs de fonctionnalité pour chaque échantillon à classer.</span><span class="sxs-lookup"><span data-stu-id="e5960-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="e5960-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5960-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5960-114">Nombre de mesures à utiliser pour estimer la probabilité de classification.</span><span class="sxs-lookup"><span data-stu-id="e5960-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="e5960-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e5960-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e5960-116">Tableau d’estimations de la probabilité de classification pour chaque échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="e5960-116">An array of estimates of the classification probability for each given sample.</span></span>