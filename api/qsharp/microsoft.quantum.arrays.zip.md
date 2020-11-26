---
uid: Microsoft.Quantum.Arrays.Zip
title: Fonction zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219853"
---
# <a name="zip-function"></a>Fonction zip

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Le fichier zip est déconseillé. Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped>.

À partir de deux tableaux, retourne un nouveau tableau de paires de sorte que chaque paire contient un élément de chaque tableau d’origine.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

## <a name="see-also"></a>Voir aussi

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. tableaux. unzippé](xref:Microsoft.Quantum.Arrays.Unzipped)