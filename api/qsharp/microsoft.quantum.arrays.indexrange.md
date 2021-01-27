---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845777"
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

## <a name="example"></a>Exemple

Les `for` boucles suivantes sont équivalentes :

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```