---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Opération SelectZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703105"
---
# <a name="selectz-operation"></a>Opération SelectZ

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Packages [](https://nuget.org/packages/)


$U unitaire $ qui applique le Pauli $Z $ Gate sur un qubits $p $ conditionné sur un état d’index $ \ket{p} $. Autrement dit, $ $ \begin{align} U\ket {p} \ Ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

L’État $ \ket{p} $ de ce registre détermine le qubit sur lequel $Z $ est appliqué.


### <a name="targetregister--qubit"></a>targetRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits sur lequel les opérateurs Pauli sont appliqués.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

