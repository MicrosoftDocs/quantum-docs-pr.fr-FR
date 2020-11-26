---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Opération PrepareArbitraryStateD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210605"
---
# <a name="preparearbitrarystated-operation"></a>Opération PrepareArbitraryStateD

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible, prépare un État sur ce registre décrit par les coefficients donnés.

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette opération prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ à partir de l’état de base de $n $-qubit $ \ket{0 \cdots 0} $.
En particulier, l’action de cette opération peut être simulée par une transformation unitaire $U $ qui agit sur l’état tous les zéros comme

$ $ \begin{align} U\ket {0... 0} & = \ket{\Psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau allant jusqu’à un maximum de $2 ^ n $. Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit enregistre les États du numéro d’encodage au format Little endian. Cette valeur est censée être initialisée dans l’état de la base de calcul $ \ket{0...0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $. `coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.

## <a name="references"></a>Références

- Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. ApproximatelyPrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)