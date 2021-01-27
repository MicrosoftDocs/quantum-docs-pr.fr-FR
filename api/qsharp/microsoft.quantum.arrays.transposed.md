---
uid: Microsoft.Quantum.Arrays.Transposed
title: Fonction transposée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850935"
---
# <a name="transposed-function"></a>Fonction transposée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la transposer d’une matrice représentée sous la forme d’un tableau de tableaux.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Description

Entrée en tant que $r \times c $ Matrix avec $r $ Rows et $c $ Columns.  La matrice est basée sur des lignes, c.-à-d., `matrix[i][j]` accède à l’élément à la ligne $i $ et column $j $.

Cette fonction retourne la matrice de $c \times r $ qui est le transposant de la matrice d’entrée.

## <a name="input"></a>Entrée

### <a name="matrix--t"></a>matrice : 't [] []

$R basée sur les lignes \times c $ Matrix



## <a name="output--t"></a>Sortie : 't [] []

$C de la matrice r $ \times transposée

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `matrix` .

## <a name="example"></a>Exemple

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```