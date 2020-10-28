---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704198"
---
# <a name="delayedca-function"></a>DelayedCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Retourne une opération qui applique l’opération donnée avec l’argument donné.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-ctl--adj"></a>OP : 't => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Opération à appliquer à la suite de l’application de la valeur de retour


### <a name="arg--t"></a>ARG : 't

Entrée à laquelle l’opération `op` est appliquée.



## <a name="output--unit--unit-ctl--adj"></a>Sortie : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Nouvelle opération qui s’applique `op` à l’entrée `arg`

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à retarder.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. retardé](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)