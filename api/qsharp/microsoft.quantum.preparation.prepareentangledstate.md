---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Opération PrepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210469"
---
# <a name="prepareentangledstate-operation"></a>Opération PrepareEntangledState

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


La paire d’une paire passe en deux registres qubit.

Autrement dit, à partir de deux registres, prépare l’état maximal pris en compte $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ entre chaque paire de qubits sur les registres respectifs, en supposant que chaque registre commence dans l’État $ \ket{0\cdots 0} $.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="left--qubit"></a>gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

