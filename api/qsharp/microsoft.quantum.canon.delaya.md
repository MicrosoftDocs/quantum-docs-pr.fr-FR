---
uid: Microsoft.Quantum.Canon.DelayA
title: Opération retardée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704243"
---
# <a name="delaya-operation"></a>Opération retardée

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une opération donnée avec un délai.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Description

Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.
En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.
`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .

## <a name="input"></a>Entrée

### <a name="op--t--unit-adj"></a>OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération à appliquer.


### <a name="arg--t"></a>ARG : 't

Entrée à laquelle l’opération est appliquée.


### <a name="aux--unit"></a>aux : [unité](xref:microsoft.quantum.lang-ref.unit)

Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à retarder.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. retardé](xref:Microsoft.Quantum.Canon.Delayed)