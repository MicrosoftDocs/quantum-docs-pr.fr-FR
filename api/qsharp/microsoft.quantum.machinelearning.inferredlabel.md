---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211778"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="8edac-102">InferredLabel fonction)</span><span class="sxs-lookup"><span data-stu-id="8edac-102">InferredLabel function</span></span>

<span data-ttu-id="8edac-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8edac-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8edac-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8edac-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="8edac-105">Étant donné un de probabilité de classification et un biais, retourne l’étiquette déduite de cette probabilité.</span><span class="sxs-lookup"><span data-stu-id="8edac-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="8edac-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8edac-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="8edac-107">biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8edac-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8edac-108">Le décalage entre deux classes, généralement le résultat de l’apprentissage d’un classifieur.</span><span class="sxs-lookup"><span data-stu-id="8edac-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="8edac-109">probabilité : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8edac-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8edac-110">Probabilités de classification pour un échantillon donné, en général résultant de l’estimation de sa fréquence de classification.</span><span class="sxs-lookup"><span data-stu-id="8edac-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="8edac-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8edac-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8edac-112">Étiquette déduite de la probabilité de classification donnée.</span><span class="sxs-lookup"><span data-stu-id="8edac-112">The label inferred from the given classification probability.</span></span>