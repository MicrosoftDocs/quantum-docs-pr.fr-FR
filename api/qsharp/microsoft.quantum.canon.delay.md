---
uid: Microsoft.Quantum.Canon.Delay
title: Opération de retardement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704254"
---
# <a name="delay-operation"></a>Opération de retardement

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une opération donnée avec un délai.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Description

Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.
En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.
`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .

## <a name="input"></a>Entrée

### <a name="op--t--u"></a>OP : 't => 'U 

Opération à appliquer.


### <a name="arg--t"></a>ARG : 't

Entrée à laquelle l’opération est appliquée.


### <a name="aux--unit"></a>aux : [unité](xref:microsoft.quantum.lang-ref.unit)

Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.



## <a name="output--u"></a>Sortie : 'U



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à retarder.
### <a name="u"></a>'U

Type de retour de l’opération à retarder.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. Quantum. Canon. retarder](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Quantum. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. Quantum. Canon. retardé](xref:Microsoft.Quantum.Canon.Delayed)