---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703954"
---
# <a name="operationpow-function"></a>OperationPow fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Élève une opération à une puissance.

Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Une opération $U $ représentant la porte à répéter.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où $U $ doit être répétée.



## <a name="output--t--unit"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de l’opération à mettre sous tension.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. Quantum. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. Quantum. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)