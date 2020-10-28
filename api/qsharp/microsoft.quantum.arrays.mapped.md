---
uid: Microsoft.Quantum.Arrays.Mapped
title: Fonction mappée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705915"
---
# <a name="mapped-function"></a>Fonction mappée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau et d’une fonction définis pour les éléments du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrée

### <a name="mapper--t---u"></a>mappeur : t-> 'U

Fonction de `'T` à `'U` qui est utilisée pour mapper des éléments.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--u"></a>Sortie : 'U []

Tableau `'U[]` d’éléments mappés par la `mapper` fonction.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.
### <a name="u"></a>'U

Type de résultat de la `mapper` fonction.

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `mapper: 'T -> 'U` nous pouvons mapper les éléments du tableau et produire un nouveau tableau de type `'U[]` .