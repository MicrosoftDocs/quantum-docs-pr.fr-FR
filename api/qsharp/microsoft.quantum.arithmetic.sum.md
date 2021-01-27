---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Opération sum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847750"
---
# <a name="sum-operation"></a>Opération sum

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémente une porte de somme réversible. À partir d’un bit de transport encodé dans qubit `carryIn` et de deux bits opérande encodés dans `summand1` et `summand2` , calcule l’opération de bits XOR de `carryIn` `summand1` et `summand2` dans le qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
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