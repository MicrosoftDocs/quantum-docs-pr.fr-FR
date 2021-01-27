---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Fonction unzippée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845383"
---
# <a name="unzipped-function"></a>Fonction unzippée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau de 2 tuples, retourne un tuple de deux tableaux, chacun contenant les éléments des tuples du tableau d’entrée.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Entrée

### <a name="arr--tu"></a>ARR : ('t, 'U) []

Tableau contenant 2 tuples



## <a name="output--tu"></a>Sortie : ('t [], 'U [])

Deux tableaux, le premier contenant tous les premiers éléments des tuples d’entrée, le second contenant tous les secondes des tuples d’entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier élément de chaque tuple
### <a name="u"></a>'U

Type du deuxième élément de chaque tuple

## <a name="example"></a>Exemple

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)