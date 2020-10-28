---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Opération RippleCarryAdderNoCarryTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706251"
---
# <a name="ripplecarryaddernocarryttk-operation"></a>Opération RippleCarryAdderNoCarryTTK

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Les ondulations réversibles, sur place, ajoutent deux entiers sans effectuer de réalisation.

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

Étant donné deux entiers de $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , l’opération calcule la somme des deux entiers modulo $2 ^ n $, où $n $ correspond à la taille en bits des entrées `xs` et `ys` . Elle ne calcule pas le bit de réalisation.

## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the First entier opérande.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir le $n les bits les moins significatifs de la somme.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération a la même fonctionnalité que RippleCarryAdderTTK, mais elle ne retourne pas le bit de transport.

## <a name="references"></a>Références

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530