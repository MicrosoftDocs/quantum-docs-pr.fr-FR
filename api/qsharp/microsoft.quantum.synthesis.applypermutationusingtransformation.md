---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Opération ApplyPermutationUsingTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858996"
---
# <a name="applypermutationusingtransformation-operation"></a>Opération ApplyPermutationUsingTransformation

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la transformation.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette procédure implémente l’approche de synthèse basée sur la transformation unidirectionnelle.  L’entrée est une permutation de $ \pi $ sur $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, qui représente une fonction booléenne réversible $n variable $.
L’algorithme effectue itérativement les étapes suivantes :

1. Recherchez la plus petite $x $, par exemple $x \ne \pi (x) = y $.
2. Recherche des opérations Toffoli à plusieurs contrôleurs, qui s’appliquent aux sorties, à savoir $ \pi (x) = x $ et ne modifient pas $ \pi (x') $ pour tous les $x' < x $

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
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Références

- [*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, pp. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, springer link, pp. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)