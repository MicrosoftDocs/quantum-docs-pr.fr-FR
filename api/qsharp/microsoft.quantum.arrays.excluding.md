---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exclusion de la fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706046"
---
# <a name="excluding-function"></a>Exclusion de la fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="remove--int"></a>Remove : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.


### <a name="array--t"></a>Tableau : 't []

Tableau dont les valeurs du tableau de sortie sont prises.



## <a name="output--t"></a>Sortie : 't []

Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau.