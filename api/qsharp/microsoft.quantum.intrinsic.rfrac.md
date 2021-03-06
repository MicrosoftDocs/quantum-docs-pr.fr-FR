---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Opération RFrac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: c80bb2b394e83c1133ed6ddc1640a3d88563ca6e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818484"
---
# <a name="rfrac-operation"></a>Opération RFrac

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applique une rotation autour de l’axe de Pauli donné par un angle spécifié comme une fraction dyadic.

\begin{align} R_ {\mu} (n, k) \mathrel{ : =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} où $ \mu \Dans \{ i, X, Y, Z \} $.

> [!WARNING]
> Cette opération utilise la Convention de signe **opposée** de @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Opérateur Pauli à élever pour former la rotation.


### <a name="numerator--int"></a>Numérateur : [int](xref:microsoft.quantum.lang-ref.int)

Numérateur dans la représentation dyadic de la fraction de l’angle par lequel le qubit doit être pivoté.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Puissance de deux spécifiant le dénominateur de l’angle par lequel le qubit doit être pivoté.


### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auquel la porte doit être appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Équivalent à :

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```