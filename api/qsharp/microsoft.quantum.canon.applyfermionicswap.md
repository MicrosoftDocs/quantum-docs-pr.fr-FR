---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Opération ApplyFermionicSWAP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845048"
---
# <a name="applyfermionicswap-operation"></a>Opération ApplyFermionicSWAP

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’échange Fermionic.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cela échange le qubits tout en appliquant une phase globale de-1 si les deux qubits sont des 1s. Préserve l’anti-symmetrization des orbites.
Voir  pour plus d'informations.

Cette opération est représentée par l’opérateur unitaire \begin{align} f_ {swap} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Entrée

### <a name="qubit1--qubit"></a>qubit1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier qubit à permuter.


### <a name="qubit2--qubit"></a>qubit2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Deuxième qubit à permuter.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv : 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Intrinsic. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)