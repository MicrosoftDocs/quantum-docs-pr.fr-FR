---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845697"
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