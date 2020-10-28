---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705963"
---
# <a name="indexrange-function"></a>IndexRange fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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