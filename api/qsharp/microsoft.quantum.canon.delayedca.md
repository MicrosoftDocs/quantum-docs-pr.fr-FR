---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207006"
---
# <a name="delayedca-function"></a>DelayedCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération qui applique l’opération donnée avec l’argument donné.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj--ctl"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération à appliquer à la suite de l’application de la valeur de retour


### <a name="arg--t"></a>ARG : 't

Entrée à laquelle l’opération `op` est appliquée.



## <a name="output--unit--unit--is-adj--ctl"></a>Sortie : l’unité d' [unité](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) est Adj + CTL

Nouvelle opération qui s’applique `op` à l’entrée `arg`

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à retarder.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. retardé](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)