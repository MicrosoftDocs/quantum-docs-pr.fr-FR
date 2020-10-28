---
uid: Microsoft.Quantum.Arrays.ForEach
title: Opération ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705998"
---
# <a name="foreach-operation"></a>Opération ForEach

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau et d’une opération définie pour les éléments du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous l’opération.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrée

### <a name="action--t--u"></a>action : 't => 'U 

Opération de `'T` à `'U` qui est appliquée à chaque élément.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--u"></a>Sortie : 'U []

Tableau `'U[]` d’éléments mappés par l' `action` opération.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.
### <a name="u"></a>'U

Type de résultat de l' `action` opération.

## <a name="remarks"></a>Notes

L’opération est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une opération, `action : 'T -> 'U` nous pouvons mapper les éléments du tableau et produire un nouveau tableau de type `'U[]` .