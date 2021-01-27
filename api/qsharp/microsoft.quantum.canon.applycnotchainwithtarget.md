---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Opération ApplyCNOTChainWithTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845113"
---
# <a name="applycnotchainwithtarget-operation"></a>Opération ApplyCNOTChainWithTarget

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule la parité d’un tableau de qubits dans un qubit cible.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Si le tableau est initialement dans l’État $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, l’état final est donné par $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.

## <a name="input"></a>Entrée

### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tableau de qubits sur lequel la parité est calculée.


### <a name="targetqubit--qubit"></a>targetQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit final dans lequel la parité de « qubits » est XOR.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

and

```qsharp
ApplyCNOTChain(qs);
```