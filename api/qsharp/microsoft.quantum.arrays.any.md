---
uid: Microsoft.Quantum.Arrays.Any
title: Toutes les fonctions
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706179"
---
# <a name="any-function"></a>Toutes les fonctions

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, vérifie si au moins un élément du tableau est conforme au prédicat.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrée

### <a name="predicate--t---bool"></a>prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Valeur de la fonction ou du prédicat appliquée à tous les éléments.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si un élément satisfait `predicate` .