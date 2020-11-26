---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Fonction unzippée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219955"
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

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)