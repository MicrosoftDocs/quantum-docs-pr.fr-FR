---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819026"
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