---
uid: Microsoft.Quantum.Arrays.EqualA
title: Fonction Equals
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706054"
---
# <a name="equala-function"></a>Fonction Equals

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir de deux tableaux du même type et d’un prédicat qui est défini pour les paires d’éléments des tableaux, vérifie si les tableaux sont égaux.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Entrée

### <a name="equal--tt---bool"></a>égal à : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de Tuple `('T, 'T)` à `Bool` qui est utilisée pour vérifier si deux éléments de tableaux sont égaux.


### <a name="array1--t"></a>matrice1 : 't []

Premier tableau à comparer.


### <a name="array2--t"></a>matrice2 : 't []

Deuxième tableau à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

Valeur `true` si et uniquement si `array1` et `array2` sont égaux.
Autrement dit, si les deux tableaux ont la même longueur et que tous les éléments sont égaux comme défini par `equal` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments de chaque tableau.

## <a name="remarks"></a>Notes

Cette fonction est définie pour les types génériques ; autrement dit, chaque fois que nous avons deux tableaux `'T[]` et une fonction `equal: ('T, 'T) -> Bool` , cette fonction retourne une `Bool` valeur qui indique si les tableaux sont égaux.
Pour que deux tableaux soient considérés comme égaux, ils doivent avoir une longueur égale et les éléments des mêmes positions dans les tableaux doivent être égaux.