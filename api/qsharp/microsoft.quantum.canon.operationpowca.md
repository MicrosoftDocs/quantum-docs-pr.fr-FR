---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852303"
---
# <a name="operationpowca-function"></a>OperationPowCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Élève une opération à une puissance.
Le modificateur `A` indique que l’opération est contrôlable et adjointable.

Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj--ctl"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Une opération $U $ représentant la porte à répéter.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où $U $ doit être répétée.



## <a name="output--t--unit--is-adj--ctl"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de l’opération à mettre sous tension.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)