---
uid: Microsoft.Quantum.Arrays.Sorted
title: Fonction triée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705787"
---
# <a name="sorted-function"></a>Fonction triée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau, retourne les éléments de ce tableau triés par une fonction de comparaison donnée.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="comparison--tt---bool"></a>Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction qui compare deux éléments de sorte que `a` est considéré comme inférieur ou égal à `b` si `comparison(a, b)` est `true` .


### <a name="array--t"></a>Tableau : 't []

Tableau à trier.



## <a name="output--t"></a>Sortie : 't []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `array` .

## <a name="remarks"></a>Notes

La fonction `comparison` est supposée être transitive, de sorte que si `comparison(a, b)` et `comparison(b, c)` , `comparison(a, c)` est utilisé par défaut. Si cette propriété ne contient pas, la sortie de cette fonction est peut-être incorrecte.

Étant donné qu’il s’agit d’une fonction, les résultats sont complètement déterministess, même lorsque deux éléments sont considérés comme égaux, `comparison` c’est-à-dire quand `comparison(a, b)` et `comparison(b, a)` sont tous les deux `true` .
En particulier, le tri effectué par cette fonction est garanti être stable, de sorte que si deux éléments `a` et `b` se produisent dans cet ordre dans `array` et sont considérés comme étant égaux `comparison` , `a` ils apparaissent également avant `b` dans la sortie.

Par exemple :

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```