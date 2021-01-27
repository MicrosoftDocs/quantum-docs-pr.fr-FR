---
uid: Microsoft.Quantum.Arrays.EqualA
title: Fonction Equals
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848691"
---
# <a name="equala-function"></a>Fonction Equals

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemple

Le code suivant vérifie si différentes paires de tableaux sont égales :

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Notes

Cette fonction est définie pour les types génériques ; autrement dit, chaque fois que nous avons deux tableaux `'T[]` et une fonction `equal: ('T, 'T) -> Bool` , cette fonction retourne une `Bool` valeur qui indique si les tableaux sont égaux.
Pour que deux tableaux soient considérés comme égaux, ils doivent avoir une longueur égale et les éléments des mêmes positions dans les tableaux doivent être égaux.