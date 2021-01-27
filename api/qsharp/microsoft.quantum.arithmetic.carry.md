---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Opération de transport
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843352"
---
# <a name="carry-operation"></a>Opération de transport

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémente une porte de transport réversible. Avec un bit de transport encodé dans qubit `carryIn` et deux bits opérande encodés dans `summand1` et `summand2` , calcule le XOR au niveau du bit de `carryIn` et `summand1` `summand2` dans le qubit `summand2` et le résultat est XOR au qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="carryin--qubit"></a>Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de transport.


### <a name="summand1--qubit"></a>summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier opérande qubit.


### <a name="summand2--qubit"></a>summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .


### <a name="carryout--qubit"></a>carryOut : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Procédez à la qubit, sera XOR avec le bit le plus élevé de la somme.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

