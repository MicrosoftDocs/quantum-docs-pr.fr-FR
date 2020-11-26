---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220958"
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