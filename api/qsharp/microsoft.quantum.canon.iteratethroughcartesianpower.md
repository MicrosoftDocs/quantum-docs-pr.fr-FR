---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Opération IterateThroughCartesianPower
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206474"
---
# <a name="iteratethroughcartesianpower-operation"></a>Opération IterateThroughCartesianPower

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération pour chaque index dans la puissance Cartésiente d’une plage d’entiers.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Description

Applique de manière itérative une opération pour chaque élément d’une puissance Cartésiene de la plage `0..(bound - 1)` .

## <a name="input"></a>Entrée

### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Puissance Cartésiene à laquelle la plage `0..(bound - 1)` doit être levée.


### <a name="bound--int"></a>lié : [entier](xref:microsoft.quantum.lang-ref.int)

Spécification de la plage sur laquelle effectuer l’itération, en fonction de la longueur de la plage.


### <a name="op--int--unit"></a>OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appeler pour chaque élément de la puissance cartésien donnée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)