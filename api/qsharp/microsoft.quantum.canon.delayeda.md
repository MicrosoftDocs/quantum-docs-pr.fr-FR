---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fonction retardée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704214"
---
# <a name="delayeda-function"></a>Fonction retardée

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Retourne une opération qui applique l’opération donnée avec l’argument donné.

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-adj"></a>OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération à appliquer à la suite de l’application de la valeur de retour


### <a name="arg--t"></a>ARG : 't

Entrée à laquelle l’opération `op` est appliquée.



## <a name="output--unit--unit-adj"></a>Sortie : [Unit](xref:microsoft.quantum.lang-ref.unit) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) d’unité

Nouvelle opération qui s’applique `op` à l’entrée `arg`

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à retarder.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. retardé](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)