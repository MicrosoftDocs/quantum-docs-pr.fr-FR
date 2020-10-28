---
uid: Microsoft.Quantum.Arrays.Filtered
title: Fonction filtrée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706043"
---
# <a name="filtered-function"></a>Fonction filtrée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, retourne un tableau qui se compose des éléments qui satisfont au prédicat.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="predicate--t---bool"></a>prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--t"></a>Sortie : 't []

Tableau `'T[]` d’éléments qui satisfont le prédicat.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et un prédicat, `'T -> Bool` nous pouvons filtrer les éléments.