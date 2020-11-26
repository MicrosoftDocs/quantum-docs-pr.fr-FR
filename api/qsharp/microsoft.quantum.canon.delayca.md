---
uid: Microsoft.Quantum.Canon.DelayCA
title: Opération DelayCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a32a4f4a3f5d0f253a4c4eaf28c67db8da978b0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207086"
---
# <a name="delayca-operation"></a>Opération DelayCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération donnée avec un délai.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.
En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.
`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .

## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj--ctl"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

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