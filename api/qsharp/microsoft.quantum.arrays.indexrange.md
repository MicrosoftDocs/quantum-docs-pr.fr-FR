---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220941"
---
# <a name="indexrange-function"></a>IndexRange fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


À partir d’un tableau, retourne une plage sur les index de ce tableau, pouvant être utilisée dans une boucle for.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Entrée

### <a name="array--telement"></a>Tableau : 'TElement []

Tableau pour lequel une plage d’index doit être retournée.



## <a name="output--range"></a>Sortie : [plage](xref:microsoft.quantum.lang-ref.range)

Plage sur tous les index du tableau.

## <a name="type-parameters"></a>Paramètres de type

### <a name="telement"></a>'TElement

Type des éléments du tableau.