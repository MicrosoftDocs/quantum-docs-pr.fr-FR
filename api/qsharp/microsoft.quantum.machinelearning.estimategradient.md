---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Opération EstimateGradient
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706510"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="60408-102">Opération EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="60408-102">EstimateGradient operation</span></span>

<span data-ttu-id="60408-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="60408-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="60408-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60408-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60408-105">Estime le dégradé d’apprentissage pour un classifieur séquentiel au niveau d’un modèle particulier et pour une entrée encodée donnée.</span><span class="sxs-lookup"><span data-stu-id="60408-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="60408-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="60408-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="60408-107">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="60408-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="60408-108">Modèle séquentiel dont le dégradé doit être estimé.</span><span class="sxs-lookup"><span data-stu-id="60408-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="60408-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="60408-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="60408-110">Entrée du classifieur séquentiel, encodée en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="60408-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="60408-111">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60408-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60408-112">Nombre de mesures à utiliser pour estimer le dégradé.</span><span class="sxs-lookup"><span data-stu-id="60408-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="60408-113">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="60408-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="60408-114">Estimation du dégradé d’apprentissage aux paramètres d’entrée et de modèle donnés.</span><span class="sxs-lookup"><span data-stu-id="60408-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="60408-115">Notes</span><span class="sxs-lookup"><span data-stu-id="60408-115">Remarks</span></span>

<span data-ttu-id="60408-116">Cette opération utilise un test Hadarmard et la technique de changement de paramètre ensemble pour estimer le dégradé.</span><span class="sxs-lookup"><span data-stu-id="60408-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>