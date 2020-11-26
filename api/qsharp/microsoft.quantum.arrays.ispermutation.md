---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220924"
---
# <a name="ispermutation-function"></a>IsPermutation fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Génère la valeur true si et seulement si un tableau donné représente une permutation.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Description

Pour un tableau `array` de longueur donné `n` , retourne true si et seulement si chaque entier de `0` à `n - 1` apparaît exactement une fois dans `array` , ce qui `array` peut être interprété comme une permutation sur les `n` éléments.

## <a name="input"></a>Entrée

### <a name="permuation--int"></a>permuation : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau qui peut ou ne peut pas représenter une permutation.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Notes

Un tableau de longueur zéro est une permutation.