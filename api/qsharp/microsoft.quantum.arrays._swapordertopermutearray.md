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
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemple

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Notes

## <a name="psuedocode"></a>Psuedocode

for (index dans 0.. length (newOrder)-1) {while newOrder [index] ! = index {Switch newOrder [index] avec newOrder [newOrder [index]]}}