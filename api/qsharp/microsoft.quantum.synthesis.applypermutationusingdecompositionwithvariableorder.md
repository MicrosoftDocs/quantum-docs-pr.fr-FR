---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Opération ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203431"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Opération ApplyPermutationUsingDecompositionWithVariableOrder

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la décomposition.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette opération est une version plus générale de @"microsoft.quantum.synthesis.applypermutationusingdecomposition" dans laquelle l’ordre des variables peut être spécifié. Un ordre des variables différent modifie la séquence de décomposition et les tables de vérité utilisées pour les portes contrôlées @"microsoft.quantum.intrinsic.x" .  Par conséquent, la modification de l’ordre des variables modifie le nombre de portes globales utilisées pour réaliser la permutation.

## <a name="input"></a>Entrée

### <a name="perm--int"></a>Perm : [int](xref:microsoft.quantum.lang-ref.int)[]

Permutation de $2 ^ n $ Elements à partir de 0.


### <a name="variableorder--int"></a>variableOrder : [int](xref:microsoft.quantum.lang-ref.int)[]

Permutation de $n $ Elements à partir de 0.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liste de $n $ qubits à laquelle la permutation est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)