---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Opération ApplyToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208837"
---
# <a name="applytofirstqubita-operation"></a>Opération ApplyToFirstQubitA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération au premier qubit dans le registre.
Le modificateur `A` indique que l’opération est adjointable.

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit--is-adj"></a>OP : [Qubit](xref:microsoft.quantum.lang-ref.qubit) l' => [unité](xref:microsoft.quantum.lang-ref.unit) qubit est ajustée

Opération à appliquer au premier qubit


### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tableau qubit vers le premier qubit auquel l’opération est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)