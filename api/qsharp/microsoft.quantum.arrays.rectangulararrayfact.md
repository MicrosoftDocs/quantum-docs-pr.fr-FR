---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845501"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une condition dans laquelle un tableau à deux dimensions a une forme rectangulaire

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Description

Cette fonction déclare que chaque ligne d’un tableau a la même longueur.

## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't [] []

Tableau d’éléments à deux dimensions


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à imprimer si le tableau n’est pas un tableau rectangulaire



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `array` .

## <a name="example"></a>Exemple

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)