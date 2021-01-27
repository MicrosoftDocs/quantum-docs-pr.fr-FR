---
uid: Microsoft.Quantum.Arrays.Zipped
title: Fonction zippée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845347"
---
# <a name="zipped-function"></a>Fonction zippée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir de deux tableaux, retourne un nouveau tableau de paires de sorte que chaque paire contient un élément de chaque tableau d’origine.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Entrée

### <a name="left--t"></a>gauche : 't []

Tableau contenant des valeurs pour le premier élément de chaque tuple.


### <a name="right--u"></a>droite : 'U []

Tableau contenant les valeurs du deuxième élément de chaque tuple.



## <a name="output--tu"></a>Sortie : ('t, 'U) []

Tableau contenant des paires de la forme `(left[idx], right[idx])` pour chacune `idx` . Si les deux tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau de gauche.
### <a name="u"></a>'U

Type des éléments du tableau de droite.

## <a name="example"></a>Exemple

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.ZipPED3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. tableaux. unzippé](xref:Microsoft.Quantum.Arrays.Unzipped)