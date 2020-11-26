---
uid: Microsoft.Quantum.Arrays.Transposed
title: Fonction transposée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219989"
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