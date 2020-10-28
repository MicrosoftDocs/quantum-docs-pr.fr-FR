---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Opération ApplyFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705379"
---
# <a name="applyfermionicswap-operation"></a>Opération ApplyFermionicSWAP

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique l’échange Fermionic.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
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

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv : 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Intrinsic. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)