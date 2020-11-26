---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210027"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Combine mappé et pli dans une fonction unique

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Description

Cette fonction itère la `fn` fonction via le tableau, en commençant à un état initial `state` et retourne toutes les valeurs intermédiaires, à l’exclusion de l’état initial.

## <a name="input"></a>Entrée

### <a name="fn--statet---state"></a>FN : ('State, t)-> 'State

Fonction à replier sur le tableau


### <a name="state--state"></a>État : 'État

État initial à replier


### <a name="array--t"></a>Tableau : 't []

Tableau de valeurs à replier



## <a name="output--state"></a>Sortie : 'State []

Tous les États intermédiaires, y compris l’état final, mais pas l’état initial.
La longueur du tableau de sortie est de la même longueur que `array` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="state"></a>'État

Le type d’État sur lequel la `fn` fonction opère, par exemple, accepte comme première entrée et retourne.
### <a name="t"></a>Peut

Type des `array` éléments.