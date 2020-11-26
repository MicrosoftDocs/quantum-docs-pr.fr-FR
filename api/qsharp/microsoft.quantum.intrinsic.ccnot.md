---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212475"
---
# <a name="ccnot-operation"></a>Opération CCNOT

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applique la porte doublement contrôlée-NOT (CCNOT) à trois qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="control1--qubit"></a>Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier contrôle qubit pour la porte CCNOT.


### <a name="control2--qubit"></a>Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Deuxième contrôle qubit pour la porte CCNOT.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cible de la porte CCNOT.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Équivalent à :

```qsharp
Controlled X([control1, control2], target);
```