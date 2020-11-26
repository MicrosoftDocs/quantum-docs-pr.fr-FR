---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220771"
---
# <a name="lookupfunction-function"></a>LookupFunction fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau, retourne une fonction qui retourne des éléments de ce tableau.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't []

Tableau à représenter sous la forme d’une fonction de recherche.



## <a name="output--int---t"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int) -> 't

Fonction de ce `f` type `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau qui est représenté comme fonction de recherche.

## <a name="remarks"></a>Notes

Cette fonction est principalement utile pour l’interopérabilité avec les fonctions et les opérations qui prennent `Int -> 'T` des fonctions comme arguments. Cela est courant, par exemple, dans la bibliothèque de représentation du générateur, où les fonctions sont utilisées pour éviter d’avoir à enregistrer un tableau entier dans la mémoire.