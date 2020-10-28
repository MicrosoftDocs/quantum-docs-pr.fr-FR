---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705659"
---
# <a name="zipped3-function"></a>Zipped3 fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir de trois tableaux, retourne un nouveau tableau de 3 tuples de sorte que chaque 3 tuple contient un élément de chaque tableau d’origine.

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Entrée

### <a name="first--t1"></a>tout d’abord : 't 1 []

Tableau contenant des valeurs pour le premier élément de chaque tuple.


### <a name="second--t2"></a>seconde : 't 2 []

Tableau contenant les valeurs du deuxième élément de chaque tuple.


### <a name="third--t3"></a>troisième : 't 3 []

Tableau contenant des valeurs pour le troisième élément de chaque tuple.



## <a name="output--t1t2t3"></a>Sortie : ('t 1, 't 2, 't 3) []

Tableau contenant 3 tuples de la forme `(first[idx], second[idx], third[idx])` pour chaque `idx` . Si les trois tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t1"></a>T 1

Type des premiers éléments du tableau.
### <a name="t2"></a>T 2

Type du deuxième élément de tableau.
### <a name="t3"></a>T 3

Type du troisième élément de tableau.

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)