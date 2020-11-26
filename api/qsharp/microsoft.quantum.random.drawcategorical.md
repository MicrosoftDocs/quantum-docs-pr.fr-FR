---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Opération DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192993"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="93ee0-102">Opération DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="93ee0-102">DrawCategorical operation</span></span>

<span data-ttu-id="93ee0-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="93ee0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="93ee0-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="93ee0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="93ee0-105">Dessine un échantillon aléatoire à partir d’une distribution catégorique spécifiée par une liste d’probablities.</span><span class="sxs-lookup"><span data-stu-id="93ee0-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="93ee0-106">Description</span><span class="sxs-lookup"><span data-stu-id="93ee0-106">Description</span></span>

<span data-ttu-id="93ee0-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="93ee0-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="93ee0-108">Les éléments de tableau qui sont égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="93ee0-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="93ee0-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="93ee0-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="93ee0-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="93ee0-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="93ee0-111">sondes : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="93ee0-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="93ee0-112">Tableau de nombres à virgule flottante proportionnel à la probabilité de sélectionner chaque index.</span><span class="sxs-lookup"><span data-stu-id="93ee0-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="93ee0-113">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93ee0-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93ee0-114">Entier $i $ avec la probabilité $ \Pr (i) = p_i/\ sum_i p_i $, où $p _i $ est le $i élément $ Th de `probs` .</span><span class="sxs-lookup"><span data-stu-id="93ee0-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="93ee0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93ee0-115">See Also</span></span>

- [<span data-ttu-id="93ee0-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="93ee0-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)