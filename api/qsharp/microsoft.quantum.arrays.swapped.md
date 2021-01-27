---
uid: Microsoft.Quantum.Arrays.Swapped
title: Permuted, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850948"
---
# <a name="swapped-function"></a>Permuted, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

