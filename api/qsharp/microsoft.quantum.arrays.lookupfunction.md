---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705910"
---
# <a name="lookupfunction-function"></a>LookupFunction fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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