---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Opération ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702118"
---
# <a name="expfrac-operation"></a>Opération ExpFrac

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique l’exponentiel d’un opérateur Pauli qubit avec un argument donné par une fraction dyadic.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} où $P _i $ est le $i élément $ Th de `paulis` , et où $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.


### <a name="numerator--int"></a>Numérateur : [int](xref:microsoft.quantum.lang-ref.int)

Numérateur ($k $) dans la représentation dyadic de la fraction de l’angle par lequel le registre qubit doit être pivoté.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Puissance de deux ($n $) spécifiant le dénominateur de l’angle par lequel le registre qubit doit être pivoté.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous pour appliquer la rotation donnée à.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

