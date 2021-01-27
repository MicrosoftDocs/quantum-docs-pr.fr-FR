---
uid: Microsoft.Quantum.Arrays.Count
title: Count (fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842851"
---
# <a name="count-function"></a>Count (fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, retourne le nombre d’éléments d’un tableau qui se compose des éléments qui satisfont au prédicat.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Entrée

### <a name="predicate--t---bool"></a>prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre d’éléments dans `array` qui satisfont le prédicat.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="example"></a>Exemple

Le code suivant illustre la fonction « count ».
Un prédicat est défini à l’aide de la @"microsoft.quantum.logical.greaterthani" fonction :

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et un prédicat, `'T -> Bool` nous pouvons filtrer les éléments.