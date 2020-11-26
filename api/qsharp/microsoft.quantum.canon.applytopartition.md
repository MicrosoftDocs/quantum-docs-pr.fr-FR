---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Opération ApplyToPartition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: f36bccb727bb38a0cdf4f1fedabc9f3f554059ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208395"
---
# <a name="applytopartition-operation"></a>Opération ApplyToPartition

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une paire d’opérations à une partition donnée d’un registre en deux parties.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="op--qubitqubit--unit"></a>OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) 

Paire d’opérations à appliquer à la partition donnée.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits de la cible à placer dans la première partie de la partition.
La qubits restante constitue la deuxième partie de la partition.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits qui sont partitionnés et exploités par les deux opérations données.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToPartitionA](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft. Quantum. Canon. ApplyToPartitionC](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft. Quantum. Canon. ApplyToPartitionCA](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)