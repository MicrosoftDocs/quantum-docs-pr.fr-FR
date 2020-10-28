---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Opération ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709206"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Opération ApplyPermutationUsingDecompositionWithVariableOrder

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la décomposition.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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