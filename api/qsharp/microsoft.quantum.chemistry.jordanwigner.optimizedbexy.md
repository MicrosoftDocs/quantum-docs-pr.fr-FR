---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Opération OptimizedBEXY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 28a7c7877a3d48fd5ba50384d7996017e7cdb14f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837243"
---
# <a name="optimizedbexy-operation"></a>Opération OptimizedBEXY

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Une $U unitaire $ qui applique la chaîne Pauli sur $ (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 $ sur qubits $0.. p $ conditionné sur un index $z \Dans \{ 0, 1 \} $ et $p $. Autrement dit, $ $ \begin{align} U\ket {z} \ Ket {p} \ Ket {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\Psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="paulibasis--qubit"></a>pauliBasis : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Quand ce qubit est dans l’État $ \ket {0} $, $X $ est appliqué. Lorsqu’il est dans l’État $ \ket {1} $, $Y $ est appliqué.


### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

L’État $ \ket{p} $ de ce registre détermine le qubit sur lequel $X $ ou $Y $ est appliqué.


### <a name="targetregister--qubit"></a>targetRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits sur lequel les opérateurs Pauli sont appliqués.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662