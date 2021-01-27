---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Fonction diagonale
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842825"
---
# <a name="diagonal-function"></a>Fonction diagonale

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un tableau d’éléments Diagonal d’un tableau à deux dimensions

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Description

Si le tableau à deux dimensions n’a pas de forme carrée, la diagonale sur le nombre minimal de lignes et de colonnes est retournée.

## <a name="input"></a>Entrée

### <a name="matrix--t"></a>matrice : 't [] []

matrice à deux dimensions dans l’ordre des lignes



## <a name="output--t"></a>Sortie : 't []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `matrix` .

## <a name="example"></a>Exemple

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. transpose](xref:Microsoft.Quantum.Arrays.Transposed)