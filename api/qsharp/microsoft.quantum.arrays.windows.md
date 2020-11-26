---
uid: Microsoft.Quantum.Arrays.Windows
title: Fonction Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219887"
---
# <a name="windows-function"></a>Fonction Windows

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne tous les sous-tableaux consécutifs de longueur `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Description

Cette fonction retourne tous les `n - size + 1` sous-tableaux de longueur `size` dans l’ordre, où `n` est la longueur de `arr` .
Les premiers sous-tableaux sont `arr[0..size - 1], arr[1..size], arr[2..size + 1]` jusqu’au dernier sous-tableau `arr[n - size..n - 1]` .

Si `size <= 0` ou `size > n` , un tableau vide est retourné.

## <a name="input"></a>Entrée

### <a name="size--int"></a>taille : [int](xref:microsoft.quantum.lang-ref.int)

Longueur des sous-tableaux.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments.



## <a name="output--t"></a>Sortie : 't [] []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.