---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703918"
---
# <a name="operationpowc-function"></a>OperationPowC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Élève une opération à une puissance.
Le modificateur `C` indique que l’opération est contrôlable.

Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-ctl"></a>OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Une opération $U $ représentant la porte à répéter.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où $U $ doit être répétée.



## <a name="output--t--unit-ctl"></a>Sortie : 't => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de l’opération à mettre sous tension.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)