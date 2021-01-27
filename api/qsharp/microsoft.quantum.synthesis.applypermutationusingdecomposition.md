---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Opération ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857390"
---
# <a name="applypermutationusingdecomposition-operation"></a>Opération ApplyPermutationUsingDecomposition

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la décomposition.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette procédure implémente l’approche de synthèse basée sur la décomposition.  L’entrée est une permutation de $ \pi $ sur $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, qui représente une fonction booléenne réversible $n $-variable.
L’algorithme exécute itérativement les étapes suivantes pour chaque index de variable $i $ :

1. Compute $ ((\ pi_l, \ pi_r), \pi') $, de telle sorte que les images de $ \ pi_l $ et $ \ pi_r $ ne changent pas les bits dans leurs éléments à des index autres que $i $ et les images de $ \pi' $ ne changent pas le bit $i $ dans leurs éléments.
2. Définissez $ \pi \leftarrow \pi' $ et dérivez les tables de vérité de $ \ pi_l $ et $ \ pi_r $ en fonction des éléments qui ne sont pas des points fixes.

Après l’application de ces étapes pour tous les index de variable, la permutation restante $ \pi $ sera l’identité, et en fonction des tables et des index de vérité collectés, vous pouvez appliquer des opérations contrôlées de table de vérité @"microsoft.quantum.intrinsic.x" à l’aide de l' @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" opération.

L’ordre des variables est $0, \dots, n-$1.  Un ordre de variable personnalisé peut être spécifié dans l’opération @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Entrée

### <a name="perm--int"></a>Perm : [int](xref:microsoft.quantum.lang-ref.int)[]

Permutation de $2 ^ n $ Elements à partir de 0.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liste de $n $ qubits à laquelle la permutation est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemple

Pour synthétiser une `SWAP` opération :

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Références

- [*Alexis de vos*, *Yvan van Rentergem*, ADV. in Math. of comm. 2 (2), 2008, pp. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *Laura tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of symbolal Computing 73 (2016), pp. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)