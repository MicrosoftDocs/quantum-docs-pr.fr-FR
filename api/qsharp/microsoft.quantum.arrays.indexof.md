---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221009"
---
# <a name="indexof-function"></a>IndexOf, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne le premier index du premier élément d’un tableau qui répond à un prédicat donné. Si aucun élément de ce type n’existe, retourne-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Entrée

### <a name="predicate--t---bool"></a>prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de prédicat agissant sur les éléments du tableau.


### <a name="arr--t"></a>ARR : 't []

Tableau dans lequel effectuer la recherche à l’aide du prédicat donné.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Soit le plus petit index `idx` , soit `predicate(arr[idx])` -1 si aucun élément de ce type n’existe.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

