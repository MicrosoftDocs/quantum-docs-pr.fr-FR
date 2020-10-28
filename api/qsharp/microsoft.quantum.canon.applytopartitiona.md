---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: Opération ApplyToPartitionA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 6ff3bf8b5a4344ee5a7a054c6285a5492260068d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704718"
---
# <a name="applytopartitiona-operation"></a>Opération ApplyToPartitionA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une paire d’opérations à une partition donnée d’un registre en deux parties.
Le modificateur `A` indique que l’opération est adjointable.

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="op--qubitqubit--unit-adj"></a>OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Paire d’opérations à appliquer à la partition donnée.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits de la cible à placer dans la première partie de la partition.
La qubits restante constitue la deuxième partie de la partition.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits qui sont partitionnés et exploités par les deux opérations données.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)