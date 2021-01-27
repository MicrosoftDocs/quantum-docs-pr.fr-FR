---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Opération CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843285"
---
# <a name="compareusingripplecarry-operation"></a>Opération CompareUsingRippleCarry

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cette opération vérifie si un entier représenté par un registre de qubits est supérieur à un autre entier, en appliquant un XOR du résultat dans un qubit de sortie.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Étant donné deux entiers `x` et `y` stockés dans des registres qubit de taille égale, cette opération vérifie si elles `x > y` répondent. Si la valeur est true, 1 est XOR dans un qubit de sortie. Dans le cas contraire, 0 est XOR dans un qubit de sortie.
En d’autres termes, cette opération peut être représentée par l’unité $ $ \begin{align} U\ket {x} \ Ket {y} \ Ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Entrée

### <a name="x--littleendian"></a>x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Premier nombre à comparer stocké au `LittleEndian` format dans un registre qubit.


### <a name="y--littleendian"></a>y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Deuxième nombre à comparer stocké au `LittleEndian` format dans un registre qubit.


### <a name="output--qubit"></a>sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit qui stocke le résultat de la comparaison $x>y $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- Un nouveau circuit d’addition d’ondulations Quantum, Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184