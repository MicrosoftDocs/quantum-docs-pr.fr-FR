---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706126"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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