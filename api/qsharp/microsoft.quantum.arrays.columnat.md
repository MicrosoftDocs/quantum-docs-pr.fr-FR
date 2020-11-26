---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210096"
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

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. transpose](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. tableaux. Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)