---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846251"
---
# <a name="columnat-function"></a>ColumnAt fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Extrait une colonne d’une matrice.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Description

Cette fonction extrait une colonne dans une matrice dans l’ordre des lignes.
L’extraction d’une ligne corrsponds vers l’accès à l’élément du premier index et ne nécessite donc aucun traitement supplémentaire.

## <a name="input"></a>Entrée

### <a name="column--int"></a>colonne : [int](xref:microsoft.quantum.lang-ref.int)

Colonne de la matrice


### <a name="matrix--t"></a>matrice : 't [] []

matrice à deux dimensions dans l’ordre des lignes



## <a name="output--t"></a>Sortie : 't []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `matrix` .

## <a name="example"></a>Exemple

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. transpose](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. tableaux. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)