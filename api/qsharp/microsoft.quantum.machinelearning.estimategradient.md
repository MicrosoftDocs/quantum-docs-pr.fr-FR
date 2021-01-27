---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Opération EstimateGradient
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844395"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="39b14-102">Opération EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="39b14-102">EstimateGradient operation</span></span>

<span data-ttu-id="39b14-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="39b14-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="39b14-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="39b14-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="39b14-105">Estime le dégradé d’apprentissage pour un classifieur séquentiel au niveau d’un modèle particulier et pour une entrée encodée donnée.</span><span class="sxs-lookup"><span data-stu-id="39b14-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="39b14-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="39b14-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="39b14-107">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="39b14-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="39b14-108">Modèle séquentiel dont le dégradé doit être estimé.</span><span class="sxs-lookup"><span data-stu-id="39b14-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="39b14-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="39b14-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="39b14-110">Entrée du classifieur séquentiel, encodée en une opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="39b14-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="39b14-111">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39b14-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39b14-112">Nombre de mesures à utiliser pour estimer le dégradé.</span><span class="sxs-lookup"><span data-stu-id="39b14-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="39b14-113">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="39b14-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="39b14-114">Estimation du dégradé d’apprentissage aux paramètres d’entrée et de modèle donnés.</span><span class="sxs-lookup"><span data-stu-id="39b14-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="39b14-115">Notes</span><span class="sxs-lookup"><span data-stu-id="39b14-115">Remarks</span></span>

<span data-ttu-id="39b14-116">Cette opération utilise un test Hadarmard et la technique de changement de paramètre ensemble pour estimer le dégradé.</span><span class="sxs-lookup"><span data-stu-id="39b14-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>