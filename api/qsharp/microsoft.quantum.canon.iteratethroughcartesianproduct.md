---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Opération IterateThroughCartesianProduct
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206440"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Opération IterateThroughCartesianProduct

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération pour chaque index dans le produit cartésien de plusieurs plages.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Description

Applique de manière itérative une opération pour chaque élément du produit cartésien de `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Entrée

### <a name="bounds--int"></a>limites : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau spécifiant les plages sur lesquelles s’effectue l’itération, chaque plage étant spécifiée comme une longueur entière.


### <a name="op--int--unit"></a>OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appeler pour chaque élément du produit cartésien donné.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)