---
uid: Microsoft.Quantum.Canon.RAll0
title: Opération RAll0
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205658"
---
# <a name="rall0-operation"></a>Opération RAll0

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Effectue une opération de décalage de phase.

$R = \boldone-(1-e ^ {i \Phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="phase--double"></a>phase : [double](xref:microsoft.quantum.lang-ref.double)

La phase $ \Phi $ appliquée à l’État $ \ket{0\cdots 0} \bra{0\cdots 0} $.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre dont l’État doit être pivoté par $R $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. RAll1](xref:Microsoft.Quantum.Canon.RAll1)