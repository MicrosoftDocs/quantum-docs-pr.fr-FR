---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220567"
---
# <a name="mostandtail-function"></a>MostAndTail fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un tuple de tous les éléments sauf un et du dernier élément du tableau.

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>Entrée

### <a name="array--a"></a>Tableau : 'A []

Tableau avec au moins un élément.



## <a name="output--aa"></a>Sortie : ('A [], 'A')

Tuple de tous les éléments sauf un et du dernier élément du tableau.

## <a name="type-parameters"></a>Paramètres de type

### <a name="a"></a>'A

Type des éléments du tableau.