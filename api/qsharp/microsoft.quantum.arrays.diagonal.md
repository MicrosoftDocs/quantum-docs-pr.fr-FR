---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Fonction diagonale
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706118"
---
# <a name="diagonal-function"></a>Fonction diagonale

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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