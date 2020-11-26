---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Fonction diagonale
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221536"
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

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. transpose](xref:Microsoft.Quantum.Arrays.Transposed)