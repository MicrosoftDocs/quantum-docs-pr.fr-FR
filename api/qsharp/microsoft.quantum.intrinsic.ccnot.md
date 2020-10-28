---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702139"
---
# <a name="ccnot-operation"></a>Opération CCNOT

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique la porte doublement contrôlée-NOT (CCNOT) à trois qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
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