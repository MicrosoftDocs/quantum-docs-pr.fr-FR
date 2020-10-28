---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Opération DrawCategorical
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706718"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="eceec-102">Opération DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="eceec-102">DrawCategorical operation</span></span>

<span data-ttu-id="eceec-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="eceec-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="eceec-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eceec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eceec-105">Dessine un échantillon aléatoire à partir d’une distribution catégorique spécifiée par une liste d’probablities.</span><span class="sxs-lookup"><span data-stu-id="eceec-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="eceec-106">Description</span><span class="sxs-lookup"><span data-stu-id="eceec-106">Description</span></span>

<span data-ttu-id="eceec-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="eceec-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="eceec-108">Les éléments de tableau qui sont égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="eceec-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="eceec-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="eceec-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="eceec-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="eceec-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="eceec-111">sondes : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eceec-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eceec-112">Tableau de nombres à virgule flottante proportionnel à la probabilité de sélectionner chaque index.</span><span class="sxs-lookup"><span data-stu-id="eceec-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="eceec-113">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eceec-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eceec-114">Entier $i $ avec la probabilité $ \Pr (i) = p_i/\ sum_i p_i $, où $p _i $ est le $i élément $ Th de `probs` .</span><span class="sxs-lookup"><span data-stu-id="eceec-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eceec-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eceec-115">See Also</span></span>

- [<span data-ttu-id="eceec-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="eceec-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)