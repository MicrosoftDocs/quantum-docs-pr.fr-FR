---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703930"
---
# <a name="operationpowa-function"></a>OperationPowA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Élève une opération à une puissance.
Le modificateur `A` indique que l’opération est adjointable.

Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-adj"></a>OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Une opération $U $ représentant la porte à répéter.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où $U $ doit être répétée.



## <a name="output--t--unit-adj"></a>Sortie : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de l’opération à mettre sous tension.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)