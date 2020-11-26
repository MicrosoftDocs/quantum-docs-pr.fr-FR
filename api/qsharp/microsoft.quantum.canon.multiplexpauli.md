---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Opération MultiplexPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: c29f7efa6b10835ce41ca4c535ec1371ac38ab63
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206031"
---
# <a name="multiplexpauli-operation"></a>Opération MultiplexPauli

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une rotation Pauli conditionnée sur un tableau de qubits.

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cela s’applique à une opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l' $P opérateur Pauli qubit $ lorsqu’il est contrôlé par le $n l’état de nombre $ \ket{j} $.
En particulier, l’action de cette opération est représentée par l’unité

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.
\end{align} $ $

## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $. Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.


### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Opérateur Pauli $P $ qui détermine l’axe de rotation.


### <a name="control--littleendian"></a>contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)