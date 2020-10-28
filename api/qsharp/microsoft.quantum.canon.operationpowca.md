---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703912"
---
# <a name="operationpowca-function"></a>OperationPowCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Élève une opération à une puissance.
Le modificateur `A` indique que l’opération est contrôlable et adjointable.

Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-ctl--adj"></a>OP : 't => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Une opération $U $ représentant la porte à répéter.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où $U $ doit être répétée.



## <a name="output--t--unit-ctl--adj"></a>Sortie : 't = [> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de l’opération à mettre sous tension.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)