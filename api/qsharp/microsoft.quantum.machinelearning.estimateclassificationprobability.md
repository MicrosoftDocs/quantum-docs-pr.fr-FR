---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Opération EstimateClassificationProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196461"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="81ebe-102">Opération EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="81ebe-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="81ebe-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="81ebe-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="81ebe-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="81ebe-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="81ebe-105">Étant donné un échantillon et un classifieur séquentiel, évalue la probabilité de classification pour cet échantillon en mesurant de manière répétée la sortie du classifieur sur l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="81ebe-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="81ebe-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="81ebe-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="81ebe-107">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81ebe-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81ebe-108">Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="81ebe-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="81ebe-109">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="81ebe-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="81ebe-110">Modèle séquentiel à utiliser pour estimer la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="81ebe-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="81ebe-111">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="81ebe-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="81ebe-112">Vecteur de fonctionnalité de l’exemple à classer.</span><span class="sxs-lookup"><span data-stu-id="81ebe-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="81ebe-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81ebe-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81ebe-114">Nombre de mesures à utiliser pour estimer la probabilité de classification.</span><span class="sxs-lookup"><span data-stu-id="81ebe-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="81ebe-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81ebe-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81ebe-116">Estimation de la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="81ebe-116">An estimate of the classification probability for the given sample.</span></span>