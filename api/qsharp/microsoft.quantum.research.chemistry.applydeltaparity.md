---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Opération ApplyDeltaParity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708642"
---
# <a name="applydeltaparity-operation"></a>Opération ApplyDeltaParity

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Packages [](https://nuget.org/packages/)


Calcule la différence de parité entre un PQRS précédent... termes et PQRS suivant... terme. Cette différence est calculée sur un qubit auxiliaire.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="prevfermionicterm--int"></a>prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]

Liste des index sur les PQRS précédents... vue.


### <a name="nextfermionicterm--int"></a>nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]

Liste des index à la PQRS suivante... vue.


### <a name="aux--qubit"></a>aux : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliaire sur lequel sont stockés les résultats du calcul de la parité.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit traité par tous les PQRS... vue.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cela suppose que les index de P < Q < R < S <... pour prevPQ et nextPQ.