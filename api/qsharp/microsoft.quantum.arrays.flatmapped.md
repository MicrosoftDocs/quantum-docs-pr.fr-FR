---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706030"
---
# <a name="flatmapped-function"></a>FlatMapped fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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