---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Opération ApplyToFirstQubitCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bc2b1275b4258b9cc2db45c9e5cfe14f7eee0c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208803"
---
# <a name="applytofirstqubitca-operation"></a>Opération ApplyToFirstQubitCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’opération op au premier qubit du Registre.
Le modificateur `CA` indique que l’opération est contrôlable et adjointable.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit--is-adj--ctl"></a>OP : [Qubit](xref:microsoft.quantum.lang-ref.qubit) l' => [unité](xref:microsoft.quantum.lang-ref.unit) qubit est Adj + CTL

Opération à appliquer au premier qubit


### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tableau qubit vers le premier qubit auquel l’opération est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)