---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Opération IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704086"
---
# <a name="iteratethroughcartesianpower-operation"></a>Opération IterateThroughCartesianPower

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


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