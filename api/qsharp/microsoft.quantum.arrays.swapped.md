---
uid: Microsoft.Quantum.Arrays.Swapped
title: Permuted, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705747"
---
# <a name="swapped-function"></a>Permuted, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Applique un échange de deux éléments dans un tableau.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="firstindex--int"></a>firstIndex : [entier](xref:microsoft.quantum.lang-ref.int)

Index du premier élément à permuter.


### <a name="secondindex--int"></a>secondIndex : [entier](xref:microsoft.quantum.lang-ref.int)

Index du deuxième élément à permuter.


### <a name="arr--t"></a>ARR : 't []

Tableau contenant les éléments à permuter.



## <a name="output--t"></a>Sortie : 't []

Tableau avec l’échange sur place appliqué.

## <a name="example"></a>Exemple

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

