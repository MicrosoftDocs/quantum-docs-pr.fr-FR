---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Opération ApproximatelyMultiplexZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704526"
---
# <a name="approximatelymultiplexz-operation"></a>Opération ApproximatelyMultiplexZ

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une rotation Pauli Z conditionnée sur un tableau de qubits, ce qui tronque les petits angles de rotation en fonction d’une tolérance donnée.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>Description

Cela applique l’opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l’opérateur Pauli qubit $Z $ lorsqu’il est contrôlé par l' $n de l’État $ \ket{j} $.
En particulier, cette opération peut être représentée par l’unité

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Entrée

### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance en dessous de laquelle les petits coefficients sont tronqués.


### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $. Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.


### <a name="control--littleendian"></a>contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.

## <a name="references"></a>Références

- Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)