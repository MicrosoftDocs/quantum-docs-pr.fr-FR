---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848409"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="bca23-102">InferredLabels fonction)</span><span class="sxs-lookup"><span data-stu-id="bca23-102">InferredLabels function</span></span>

<span data-ttu-id="bca23-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bca23-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bca23-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bca23-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bca23-105">Étant donné un tableau de probabilités de classification et un décalage, retourne l’étiquette déduite de chaque probabilité.</span><span class="sxs-lookup"><span data-stu-id="bca23-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="bca23-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="bca23-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="bca23-107">biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bca23-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bca23-108">Le décalage entre deux classes, généralement le résultat de l’apprentissage d’un classifieur.</span><span class="sxs-lookup"><span data-stu-id="bca23-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="bca23-109">probabilités : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bca23-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bca23-110">Tableau des probabilités de classification pour un ensemble d’exemples, en général résultant de l’estimation des fréquences de classification.</span><span class="sxs-lookup"><span data-stu-id="bca23-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="bca23-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bca23-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bca23-112">Étiquette déduite à partir de chaque probabilité de classification.</span><span class="sxs-lookup"><span data-stu-id="bca23-112">The label inferred from each classification probability.</span></span>