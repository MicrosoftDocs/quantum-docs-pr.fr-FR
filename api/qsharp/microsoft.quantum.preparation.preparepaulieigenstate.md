---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Opération PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193690"
---
# <a name="preparepaulieigenstate-operation"></a>Opération PreparePauliEigenstate

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prépare un qubit dans le eigenstate positif d’un opérateur Pauli donné.
Si l’opérateur d’identité est donné, le qubit est préparé dans l’état de la même façon.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Description

Si le qubit a été initialement dans l’État $ \ket {0} $, cette opération prépare le qubit dans le eigenstate $ + $1 d’un opérateur Pauli donné, ou, pour `PauliI` , dans l’état le plus maximal mélangé à la place (consultez <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Si le qubit était dans un État autre que $ \ket {0} $, cette opération applique les portes suivantes : $H $ pour `PauliX` , $HS $ pour `PauliY` , $I $ pour `PauliZ` et <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pour `PauliI` .

## <a name="input"></a>Entrée

### <a name="basis--pauli"></a>base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un opérateur Pauli $P $.


### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit à préparer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

