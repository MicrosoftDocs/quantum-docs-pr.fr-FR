---
uid: Microsoft.Quantum.Canon.Compose
title: Compose, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840903"
---
# <a name="compose-function"></a>Compose, fonction

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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