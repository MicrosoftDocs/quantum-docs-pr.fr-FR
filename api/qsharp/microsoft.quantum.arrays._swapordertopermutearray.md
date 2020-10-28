---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706190"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="c5263-102">_SwapOrderToPermuteArray fonction)</span><span class="sxs-lookup"><span data-stu-id="c5263-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="c5263-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5263-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5263-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5263-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5263-105">Retourne les éléments Order d’un tableau qui doivent être permutés pour produire un tableau ordonné.</span><span class="sxs-lookup"><span data-stu-id="c5263-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="c5263-106">Suppose que des permutations sont en place.</span><span class="sxs-lookup"><span data-stu-id="c5263-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c5263-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c5263-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="c5263-108">newOrder : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5263-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5263-109">Tableau avec la permutation des index du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="c5263-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="c5263-110">Il doit y avoir $n $ Elements, chacun étant un entier unique compris entre $0 $ et $n-$1.</span><span class="sxs-lookup"><span data-stu-id="c5263-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="c5263-111">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c5263-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c5263-112">Le tuple représente les deux index à permuter.</span><span class="sxs-lookup"><span data-stu-id="c5263-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="c5263-113">Les permutations commencent à l’index le plus bas.</span><span class="sxs-lookup"><span data-stu-id="c5263-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5263-114">Notes</span><span class="sxs-lookup"><span data-stu-id="c5263-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="c5263-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="c5263-115">Psuedocode</span></span>

<span data-ttu-id="c5263-116">for (index dans 0.. length (newOrder)-1) {while newOrder [index] ! = index {Switch newOrder [index] avec newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="c5263-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>