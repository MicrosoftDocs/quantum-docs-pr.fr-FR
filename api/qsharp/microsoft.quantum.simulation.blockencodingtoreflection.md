---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847258"
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