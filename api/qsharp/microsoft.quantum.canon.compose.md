---
uid: Microsoft.Quantum.Canon.Compose
title: Compose, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704355"
---
# <a name="compose-function"></a>Compose, fonction

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Retourne la composition de deux fonctions.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Description

À partir de deux fonctions $f $ et $g $, retourne une nouvelle fonction représentant $f \circ g $.

## <a name="input"></a>Entrée

### <a name="outer--u---v"></a>externe : 'U-> 'V

Deuxième fonction à appliquer.


### <a name="inner--t---u"></a>interne : t-> 'U

Première fonction à appliquer.



## <a name="output--t---v"></a>Sortie : 't-> 'V

Une nouvelle fonction $h $ de telle sorte que toutes les entrées $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de la première fonction à appliquer.
### <a name="u"></a>'U

Type de sortie de la première fonction à appliquer et type d’entrée de la deuxième fonction à appliquer.
### <a name="v"></a>'V

Type de sortie de la deuxième fonction à appliquer.