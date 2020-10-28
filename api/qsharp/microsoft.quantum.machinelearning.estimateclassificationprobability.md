---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Opération EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701383"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="05c31-102">Opération EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="05c31-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="05c31-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="05c31-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="05c31-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05c31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05c31-105">Étant donné un échantillon et un classifieur séquentiel, évalue la probabilité de classification pour cet échantillon en mesurant de manière répétée la sortie du classifieur sur l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="05c31-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="05c31-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="05c31-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="05c31-107">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05c31-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05c31-108">Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="05c31-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="05c31-109">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="05c31-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="05c31-110">Modèle séquentiel à utiliser pour estimer la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="05c31-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="05c31-111">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="05c31-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="05c31-112">Vecteur de fonctionnalité de l’exemple à classer.</span><span class="sxs-lookup"><span data-stu-id="05c31-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="05c31-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05c31-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05c31-114">Nombre de mesures à utiliser pour estimer la probabilité de classification.</span><span class="sxs-lookup"><span data-stu-id="05c31-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="05c31-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05c31-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05c31-116">Estimation de la probabilité de classification pour l’échantillon donné.</span><span class="sxs-lookup"><span data-stu-id="05c31-116">An estimate of the classification probability for the given sample.</span></span>