---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Opération PrepareUniformSuperposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854318"
---
# <a name="prepareuniformsuperposition-operation"></a>Opération PrepareUniformSuperposition

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée une superposition uniforme sur les États qui encodent 0 à `nIndices - 1` .

Autrement dit, ce $U unitaire $ crée une superposition uniforme sur tous les États numériques $0 $ à $M-$1, étant donné un état d’entrée $ \ket{0\cdots 0} $. En d’autres termes, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="nindices--int"></a>nIndices : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre souhaité d’États $M $ dans la superposition uniforme.


### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre qubit qui stocke les États du nombre au `LittleEndian` format.
Ce registre doit être en mesure de stocker le nombre $M-$1, et est supposé être initialisé à l’État $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemple

L’exemple suivant prépare l’État $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ sur $3 $ qubits.

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>Notes

L’opération est adjointable, mais requiert `indexRegister` une superposition uniforme sur les États de la première `nIndices` base dans ce cas.