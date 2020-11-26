---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221247"
---
# <a name="flatmapped-function"></a>FlatMapped fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau et d’une fonction qui mappent un élément de tableau à un tableau de sortie, retourne les tableaux de sortie concaténés pour chaque élément de tableau.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Entrée

### <a name="mapper--tinput---toutput"></a>mappeur : 'TInput-> 'TOutput []

Fonction de `'TInput` à `'TOutput[]` qui est utilisée pour mapper des éléments de tableau.


### <a name="array--tinput"></a>Tableau : 'TInput []

Tableau d’éléments.



## <a name="output--toutput"></a>Sortie : 'TOutput []

Tableau de `'TOutput[]` qui est la concaténation de tous les tableaux générés par la fonction de mappage.

## <a name="type-parameters"></a>Paramètres de type

### <a name="tinput"></a>'TInput

Type des `array` éléments.
### <a name="toutput"></a>«TOutput

La `mapper` fonction retourne des tableaux de ce type.