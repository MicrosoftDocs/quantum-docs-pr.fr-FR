---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846291"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="a55c0-102">_SwapOrderToPermuteArray fonction)</span><span class="sxs-lookup"><span data-stu-id="a55c0-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="a55c0-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a55c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a55c0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a55c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a55c0-105">Retourne les éléments Order d’un tableau qui doivent être permutés pour produire un tableau ordonné.</span><span class="sxs-lookup"><span data-stu-id="a55c0-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="a55c0-106">Suppose que des permutations sont en place.</span><span class="sxs-lookup"><span data-stu-id="a55c0-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="a55c0-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="a55c0-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="a55c0-108">newOrder : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a55c0-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a55c0-109">Tableau avec la permutation des index du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="a55c0-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="a55c0-110">Il doit y avoir $n $ Elements, chacun étant un entier unique compris entre $0 $ et $n-$1.</span><span class="sxs-lookup"><span data-stu-id="a55c0-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="a55c0-111">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a55c0-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="a55c0-112">Le tuple représente les deux index à permuter.</span><span class="sxs-lookup"><span data-stu-id="a55c0-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="a55c0-113">Les permutations commencent à l’index le plus bas.</span><span class="sxs-lookup"><span data-stu-id="a55c0-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="a55c0-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="a55c0-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="a55c0-115">Notes</span><span class="sxs-lookup"><span data-stu-id="a55c0-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="a55c0-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="a55c0-116">Psuedocode</span></span>

<span data-ttu-id="a55c0-117">for (index dans 0.. length (newOrder)-1) {while newOrder [index] ! = index {Switch newOrder [index] avec newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="a55c0-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>