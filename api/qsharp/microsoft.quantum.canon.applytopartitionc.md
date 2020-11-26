---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Opération ApplyToPartitionC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 22af7a3704f88a4d1973149e7387ebb683468540
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208267"
---
# <a name="applytopartitionc-operation"></a>Opération ApplyToPartitionC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une paire d’opérations à une partition donnée d’un registre en deux parties.
Le modificateur `C` indique que l’opération est contrôlable.

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="op--qubitqubit--unit--is-ctl"></a>OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Paire d’opérations à appliquer à la partition donnée.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits de la cible à placer dans la première partie de la partition.
La qubits restante constitue la deuxième partie de la partition.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits qui sont partitionnés et exploités par les deux opérations données.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)