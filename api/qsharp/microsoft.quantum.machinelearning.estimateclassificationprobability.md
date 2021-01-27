---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Opération EstimateClassificationProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853939"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="db308-102">Opération EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="db308-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="db308-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db308-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="db308-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db308-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="db308-105">Étant donné un échantillon et un classifieur séquentiel, évalue la probabilité de classification pour cet échantillon en mesurant de manière répétée la sortie du classifieur sur l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="db308-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="db308-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="db308-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="db308-107">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db308-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db308-108">Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="db308-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="db308-109">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="db308-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="db308-110">Modèle séquentiel à utiliser pour estimer la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="db308-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="db308-111">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="db308-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="db308-112">Vecteur de fonctionnalité de l’exemple à classer.</span><span class="sxs-lookup"><span data-stu-id="db308-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="db308-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db308-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db308-114">Nombre de mesures à utiliser pour estimer la probabilité de classification.</span><span class="sxs-lookup"><span data-stu-id="db308-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="db308-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db308-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db308-116">Estimation de la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="db308-116">An estimate of the classification probability for the given sample.</span></span>