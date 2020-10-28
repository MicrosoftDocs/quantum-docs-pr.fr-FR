---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705979"
---
# <a name="indexof-function"></a>IndexOf, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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

