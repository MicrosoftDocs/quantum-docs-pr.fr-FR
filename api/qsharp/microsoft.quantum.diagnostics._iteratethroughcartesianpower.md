---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: opération de _iterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702826"
---
# <a name="_iteratethroughcartesianpower-operation"></a>opération de _iterateThroughCartesianPower

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Itère une variable à l’aide d’un produit cartésien [0, limites [0]-1] × [0, limites [1]-1] × [0, limites [longueur (limites)-1]-1] et appelle op (arr) pour chaque élément du produit cartésien

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Entrée

### <a name="length--int"></a>Longueur : [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

