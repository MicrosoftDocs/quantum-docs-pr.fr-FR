---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221077"
---
# <a name="headandrest-function"></a>HeadAndRest fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un tuple du premier et de tous les éléments restants du tableau.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Entrée

### <a name="array--a"></a>Tableau : 'A []

Tableau avec au moins un élément.



## <a name="output--aa"></a>Sortie : ('A, 'A [])

Tuple du premier et de tous les éléments restants du tableau.

## <a name="type-parameters"></a>Paramètres de type

### <a name="a"></a>'A

Type des éléments du tableau.