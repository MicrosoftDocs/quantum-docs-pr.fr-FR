---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225344"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit un `BlockEncoding` en un équivalent `BLockEncodingReflection` .

Autrement dit, étant donné un `BlockEncoding` $U unitaire $ qui encode un opérateur $H $ d’intérêt, le convertit en un `BlockEncodingReflection` $U' $ qui encode le même opérateur, mais satisfait également $U' ^ \Dagger = U' $.
Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Entrée

### <a name="blockencoding--blockencoding"></a>blockEncoding : [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`$U unitaire $ à convertir en réflexion.



## <a name="output--blockencodingreflection"></a>Sortie : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Un $U unitaire' $ agit conjointement sur `a` les registres et `s` qui encodent le bloc $H $, et satisfont $U' ^ \Dagger = U' $.

## <a name="remarks"></a>Notes

Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.

## <a name="references"></a>Références

- Simulation de la Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)