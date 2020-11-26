---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Opération PermuteQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205600"
---
# <a name="permutequbits-operation"></a>Opération PermuteQubits

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permute qubits à l’aide de l’opération d’échange.

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="ordering--int"></a>classement : [int](xref:microsoft.quantum.lang-ref.int)[]

Décrit le nouveau classement du qubits, où qubit à l’index i se trouve maintenant à l’ordre [i].


### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit Inscrivez-vous pour être traité.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

