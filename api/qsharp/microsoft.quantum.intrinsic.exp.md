---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Opération exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702133"
---
# <a name="exp-operation"></a>Opération exp

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique l’exponentiel d’un opérateur qubit Pauli.

\begin{align} e ^ {i \Theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} où $P _i $ est le $i élément $ Th de `paulis` , et où $N = $ `Length(paulis)` .

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.


### <a name="theta--double"></a>thêta : [double](xref:microsoft.quantum.lang-ref.double)

Angle à l’aide de l’opérateur Pauli qubit donné par lequel le registre cible doit pivoter.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous pour appliquer la rotation donnée à.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

