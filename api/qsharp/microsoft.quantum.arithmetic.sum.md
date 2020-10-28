---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Opération sum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706198"
---
# <a name="sum-operation"></a>Opération sum

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Implémente une porte de somme réversible. À partir d’un bit de transport encodé dans qubit `carryIn` et de deux bits opérande encodés dans `summand1` et `summand2` , calcule l’opération de bits XOR de `carryIn` `summand1` et `summand2` dans le qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="carryin--qubit"></a>Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de transport.


### <a name="summand1--qubit"></a>summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier opérande qubit.


### <a name="summand2--qubit"></a>summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Contrairement à l' `Carry` opération, cela ne calcule pas le bit de report.