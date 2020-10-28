---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: opération de _prepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702823"
---
# <a name="_prepareentangledstate-operation"></a>opération de _prepareEntangledState

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


À partir de deux registres, prépare l’état de l’enchevêtrement maximal entre chaque paire de qubits sur les registres respectifs.
Toutes les qubits doivent démarrer dans l’État | 0 ⟩.

Le résultat est que les paires correspondantes de qubits de chaque registre se trouvent dans la variable $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="left--qubit"></a>gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

