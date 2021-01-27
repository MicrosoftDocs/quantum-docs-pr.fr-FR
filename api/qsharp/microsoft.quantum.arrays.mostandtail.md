---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845601"
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