---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220686"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="e5167-102">MappedOverRange fonction)</span><span class="sxs-lookup"><span data-stu-id="e5167-102">MappedOverRange function</span></span>

<span data-ttu-id="e5167-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e5167-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e5167-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5167-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5167-105">Pour une plage et une fonction qui acceptent un entier comme entrée, retourne un nouveau tableau qui se compose des images des valeurs de plage sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="e5167-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e5167-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e5167-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="e5167-107">mappeur : [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="e5167-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="e5167-108">Fonction de `Int` à `'T` qui est utilisée pour mapper des valeurs de plage.</span><span class="sxs-lookup"><span data-stu-id="e5167-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="e5167-109">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e5167-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e5167-110">Plage d’entiers.</span><span class="sxs-lookup"><span data-stu-id="e5167-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="e5167-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="e5167-111">Output : 'T[]</span></span>

<span data-ttu-id="e5167-112">Tableau `'T[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="e5167-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5167-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e5167-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5167-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e5167-114">'T</span></span>

<span data-ttu-id="e5167-115">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="e5167-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5167-116">Notes</span><span class="sxs-lookup"><span data-stu-id="e5167-116">Remarks</span></span>

<span data-ttu-id="e5167-117">La fonction est définie pour les types génériques, autrement dit, chaque fois que nous avons une fonction, `mapper: Int -> 'T` nous pouvons mapper les valeurs de la plage et produire un tableau de type `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="e5167-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5167-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5167-118">See Also</span></span>

- [<span data-ttu-id="e5167-119">Microsoft. Quantum. Arrays. mapped</span><span class="sxs-lookup"><span data-stu-id="e5167-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)