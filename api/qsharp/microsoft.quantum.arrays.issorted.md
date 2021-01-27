---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845739"
---
# <a name="issorted-function"></a><span data-ttu-id="2627e-102">IsSorted fonction)</span><span class="sxs-lookup"><span data-stu-id="2627e-102">IsSorted function</span></span>

<span data-ttu-id="2627e-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2627e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2627e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2627e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2627e-105">À partir d’un tableau, retourne si ce tableau est trié comme défini par une fonction de comparaison donnée.</span><span class="sxs-lookup"><span data-stu-id="2627e-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="2627e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2627e-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="2627e-107">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2627e-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2627e-108">Fonction qui compare deux éléments de sorte que `a` est considéré comme inférieur ou égal à `b` si `comparison(a, b)` est `true` .</span><span class="sxs-lookup"><span data-stu-id="2627e-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2627e-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="2627e-109">array : 'T[]</span></span>

<span data-ttu-id="2627e-110">Tableau à vérifier.</span><span class="sxs-lookup"><span data-stu-id="2627e-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2627e-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2627e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2627e-112">`true` Si et seulement si pour chaque paire d’éléments `a` et `b` si `array` se produit dans cet ordre, `comparison(a, b)` est `true` .</span><span class="sxs-lookup"><span data-stu-id="2627e-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2627e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2627e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2627e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2627e-114">'T</span></span>

<span data-ttu-id="2627e-115">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="2627e-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2627e-116">Notes</span><span class="sxs-lookup"><span data-stu-id="2627e-116">Remarks</span></span>

<span data-ttu-id="2627e-117">La fonction `comparison` est supposée être transitive, de sorte que si `comparison(a, b)` et `comparison(b, c)` , `comparison(a, c)` est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="2627e-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="2627e-118">Si cette propriété ne contient pas, la sortie de cette fonction est peut-être incorrecte.</span><span class="sxs-lookup"><span data-stu-id="2627e-118">If this property does not hold, then the output of this function may be incorrect.</span></span>