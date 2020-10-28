---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705958"
---
# <a name="interleaved-function"></a>Fonction entrelacée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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