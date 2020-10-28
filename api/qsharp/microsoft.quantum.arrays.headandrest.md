---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705982"
---
# <a name="headandrest-function"></a>HeadAndRest fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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