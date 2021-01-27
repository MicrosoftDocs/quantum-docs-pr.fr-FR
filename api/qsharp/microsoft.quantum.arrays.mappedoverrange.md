---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845654"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="61dd1-102">MappedOverRange fonction)</span><span class="sxs-lookup"><span data-stu-id="61dd1-102">MappedOverRange function</span></span>

<span data-ttu-id="61dd1-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="61dd1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="61dd1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61dd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61dd1-105">Pour une plage et une fonction qui acceptent un entier comme entrée, retourne un nouveau tableau qui se compose des images des valeurs de plage sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="61dd1-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="61dd1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="61dd1-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="61dd1-107">mappeur : [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="61dd1-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="61dd1-108">Fonction de `Int` à `'T` qui est utilisée pour mapper des valeurs de plage.</span><span class="sxs-lookup"><span data-stu-id="61dd1-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="61dd1-109">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="61dd1-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="61dd1-110">Plage d’entiers.</span><span class="sxs-lookup"><span data-stu-id="61dd1-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="61dd1-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="61dd1-111">Output : 'T[]</span></span>

<span data-ttu-id="61dd1-112">Tableau `'T[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="61dd1-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61dd1-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="61dd1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61dd1-114">Peut</span><span class="sxs-lookup"><span data-stu-id="61dd1-114">'T</span></span>

<span data-ttu-id="61dd1-115">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="61dd1-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="61dd1-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="61dd1-116">Example</span></span>

<span data-ttu-id="61dd1-117">Cet exemple ajoute 1 à une plage de nombres pairs :</span><span class="sxs-lookup"><span data-stu-id="61dd1-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="61dd1-118">Notes</span><span class="sxs-lookup"><span data-stu-id="61dd1-118">Remarks</span></span>

<span data-ttu-id="61dd1-119">La fonction est définie pour les types génériques, autrement dit, chaque fois que nous avons une fonction, `mapper: Int -> 'T` nous pouvons mapper les valeurs de la plage et produire un tableau de type `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="61dd1-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="61dd1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61dd1-120">See Also</span></span>

- [<span data-ttu-id="61dd1-121">Microsoft. Quantum. Arrays. mapped</span><span class="sxs-lookup"><span data-stu-id="61dd1-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)