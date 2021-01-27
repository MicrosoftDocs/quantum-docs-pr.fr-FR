---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848641"
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

## <a name="example"></a>Exemple

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```