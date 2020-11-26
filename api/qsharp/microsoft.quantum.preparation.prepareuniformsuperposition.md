---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Opération PrepareUniformSuperposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230087"
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



## <a name="remarks"></a>Notes

L’opération est adjointable, mais requiert `indexRegister` une superposition uniforme sur les États de la première `nIndices` base dans ce cas.