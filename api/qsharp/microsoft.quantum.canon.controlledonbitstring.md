---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840804"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération unitaire qui applique un Oracle sur le registre cible si l’état du registre de contrôle correspond à un masque de bits spécifié.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Description

La sortie de cette fonction est une opération qui peut être représentée par une transformation unitaire $U $ telle que \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\Psi} = \ket{b_0 B_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\Psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\Psi} & \textrm{otherwise} \end{cases}, \end{align} où $V $ est une transformation unitaire qui représente l’action de l' `oracle` opération.

## <a name="input"></a>Entrée

### <a name="bits--bool"></a>bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Chaîne de bits pour contrôler l’opération unitaire donnée.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération unitaire à appliquer sur le registre cible.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond au masque de bits `bits` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="example"></a>Exemple

Les extraits de code suivants sont équivalents :

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

and

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

Le code suivant prépare un État $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $ :

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Notes

Le modèle donné par `bits` peut être plus petit que `controlRegister` , auquel cas des qubits de contrôle supplémentaires sont ignorés (c’est-à-dire qu’ils ne sont ni contrôlés sur $ \ket {0} $, ni sur $ \ket {1} $).
Si `bits` est plus long que `controlRegister` , une erreur est générée.

Avec un tableau booléen `bits` et une opération unitaire `oracle` , la sortie de cette fonction est une opération qui effectue les étapes suivantes :

* Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à `false` l’élément de `bits` ;
* appliquer `Controlled oracle` aux registres de contrôle et cibles ;
* Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à l' `false` élément de à `bits` nouveau pour ramener le registre de contrôle à l’état d’origine.

La sortie du `Controlled` functor est un cas particulier `ControlledOnBitString` où `bits` est égal à `[true, ..., true]` .