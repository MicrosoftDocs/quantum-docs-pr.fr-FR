---
uid: Microsoft.Quantum.Arrays.All
title: Fonction All
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842894"
---
# <a name="all-function"></a>Fonction All

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, et vérifie si tous les éléments du tableau répondent au prédicat.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrée

### <a name="predicate--t---bool"></a>prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Valeur de la fonction et du prédicat appliquée à tous les éléments.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="example"></a>Exemple

Le code suivant vérifie si tous les éléments du tableau sont non nuls :

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si tous les éléments répondent `predicate` .