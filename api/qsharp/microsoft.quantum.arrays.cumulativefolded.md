---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846241"
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

## <a name="example"></a>Exemple

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```