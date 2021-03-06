---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: opération de _prepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830986"
---
# <a name="_prepareentangledstate-operation"></a>opération de _prepareEntangledState

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


À partir de deux registres, prépare l’état de l’enchevêtrement maximal entre chaque paire de qubits sur les registres respectifs.
Toutes les qubits doivent démarrer dans l’État | 0 ⟩.

Le résultat est que les paires correspondantes de qubits de chaque registre se trouvent dans la variable $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="left--qubit"></a>gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un tableau qubit dans l’État $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

