---
uid: Microsoft.Quantum.Arrays.Transposed
title: Fonction transposée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705739"
---
# <a name="transposed-function"></a>Fonction transposée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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