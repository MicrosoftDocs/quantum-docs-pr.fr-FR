---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Opération ApplyPauliFromBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209058"
---
# <a name="applypaulifrombitstring-operation"></a>Opération ApplyPauliFromBitString

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique un opérateur Pauli sur chaque qubit d’un tableau si le bit correspondant d’un tableau booléen correspond à une entrée donnée.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Opérateur Pauli à appliquer à `qubits[idx]` Where `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply : [bool](xref:microsoft.quantum.lang-ref.bool)

appliquer Pauli si le bit est cette valeur


### <a name="bits--bool"></a>bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Registre booléen spécifiant le qubit correspondant dans lequel `qubits` doit être traité


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre quantique sur lequel appliquer de manière sélective l’opérateur Pauli spécifié



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Le tableau booléen et le registre Quantum doivent être de longueur égale.