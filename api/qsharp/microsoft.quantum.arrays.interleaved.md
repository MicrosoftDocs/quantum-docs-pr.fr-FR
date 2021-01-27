---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848110"
---
# <a name="interleaved-function"></a>Fonction entrelacée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entrelace deux tableaux de (presque) la même taille.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Description

Cette fonction retourne l’entrelacement de deux tableaux, en commençant par le premier élément du premier tableau, puis le premier élément du deuxième tableau, et ainsi de suite.

Le premier tableau doit être de la même longueur que le second, ou peut avoir un élément supplémentaire.

## <a name="input"></a>Entrée

### <a name="first--t"></a>tout d’abord : 't []

Premier tableau à entrelacer.


### <a name="second--t"></a>seconde : 't []

Deuxième tableau à entrelacer.



## <a name="output--t"></a>Sortie : 't []

Tableau entrelacé

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `first` et `second` .

## <a name="example"></a>Exemple

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```