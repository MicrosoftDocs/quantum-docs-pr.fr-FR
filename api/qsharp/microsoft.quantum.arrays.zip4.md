---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: c9dd07ddc63f1d75952d3841997eed0f78e054b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219785"
---
# <a name="zip4-function"></a>Zip4 fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip4 est déconseillé. Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped4>.

À partir de quatre tableaux, retourne un nouveau tableau de 4 tuples de telle sorte que chaque 4 tuple contient un élément de chaque tableau d’origine.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Entrée

### <a name="first--t1"></a>tout d’abord : 't 1 []

Tableau contenant des valeurs pour le premier élément de chaque tuple.


### <a name="second--t2"></a>seconde : 't 2 []

Tableau contenant les valeurs du deuxième élément de chaque tuple.


### <a name="third--t3"></a>troisième : 't 3 []

Tableau contenant des valeurs pour le troisième élément de chaque tuple.


### <a name="fourth--t4"></a>quatrième : t 4 []

Tableau contenant les valeurs du quatrième élément de chaque tuple.



## <a name="output--t1t2t3t4"></a>Sortie : ('t 1, 't 2, 't 3, 't 4) []

Tableau contenant 4 tuples de la forme `(first[idx], second[idx], third[idx], fourth[idx])` pour chaque `idx` . Si les quatre tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t1"></a>T 1

Type des premiers éléments du tableau.
### <a name="t2"></a>T 2

Type du deuxième élément de tableau.
### <a name="t3"></a>T 3

Type du troisième élément de tableau.
### <a name="t4"></a>T 4

Type du quatrième élément de tableau.

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)