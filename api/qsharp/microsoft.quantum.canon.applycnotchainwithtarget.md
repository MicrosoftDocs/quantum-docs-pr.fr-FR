---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Opération ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705438"
---
# <a name="applycnotchainwithtarget-operation"></a>Opération ApplyCNOTChainWithTarget

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Calcule la parité d’un tableau de qubits dans un qubit cible.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
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

et

```qsharp
ApplyCNOTChain(qs);
```