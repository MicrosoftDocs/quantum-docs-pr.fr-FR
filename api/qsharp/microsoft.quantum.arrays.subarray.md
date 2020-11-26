---
uid: Microsoft.Quantum.Arrays.Subarray
title: SubArray, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220159"
---
# <a name="subarray-function"></a>SubArray, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prend un tableau et une liste d’emplacements et produit un nouveau tableau formé à partir des éléments du tableau d’origine qui correspondent aux emplacements donnés.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="indices--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)[]

Liste d’entiers utilisée pour définir le sous-tableau.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--t"></a>Sortie : 't []

Tableau `out` d’éléments dont les index correspondent au sous-tableau, de telle sorte que `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une liste d’emplacements `Int[]` définissant le sous-tableau.
La construction du sous-tableau est basée sur la génération d’une nouvelle copie complète du tableau donné au lieu de conserver les références.

Si `Length(indices) < Length(array)` la condition est, cette fonction retourne un sous-ensemble de `array` . En revanche, si contient des `indices` éléments répétés, les éléments correspondants de `array` sont de la même façon répétés.
Si `indices` et `array` sont de la même longueur, cette fonction fournit des permutations de `array` .