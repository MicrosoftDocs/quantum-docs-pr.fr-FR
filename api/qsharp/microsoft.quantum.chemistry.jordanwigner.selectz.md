---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Opération SelectZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224715"
---
# <a name="selectz-operation"></a>Opération SelectZ

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


$U unitaire $ qui applique le Pauli $Z $ Gate sur un qubits $p $ conditionné sur un état d’index $ \ket{p} $. Autrement dit, $ $ \begin{align} U\ket {p} \ Ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

L’État $ \ket{p} $ de ce registre détermine le qubit sur lequel $Z $ est appliqué.


### <a name="targetregister--qubit"></a>targetRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits sur lequel les opérateurs Pauli sont appliqués.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

