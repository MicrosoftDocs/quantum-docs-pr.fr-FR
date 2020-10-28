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
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Retourne les éléments Order d’un tableau qui doivent être permutés pour produire un tableau ordonné.
Suppose que des permutations sont en place.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Entrée

### <a name="neworder--int"></a>newOrder : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau avec la permutation des index du nouveau tableau. Il doit y avoir $n $ Elements, chacun étant un entier unique compris entre $0 $ et $n-$1.



## <a name="output--intint"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Le tuple représente les deux index à permuter. Les permutations commencent à l’index le plus bas.

## <a name="remarks"></a>Notes

## <a name="psuedocode"></a>Psuedocode

for (index dans 0.. length (newOrder)-1) {while newOrder [index] ! = index {Switch newOrder [index] avec newOrder [newOrder [index]]}}