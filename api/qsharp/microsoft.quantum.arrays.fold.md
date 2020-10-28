---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706003"
---
# <a name="fold-function"></a>Fold, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Itère une fonction `f` via un tableau `array` , en retournant `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Entrée

### <a name="folder--statet---state"></a>dossier : (« État, t)-> » État

Fonction à plier sur le tableau.


### <a name="state--state"></a>État : 'État

État initial du dossier.


### <a name="array--t"></a>Tableau : 't []

Tableau de valeurs à replier.



## <a name="output--state"></a>Sortie : 'State

État final retourné par le dossier après l’itération sur tous les éléments de `array` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="state"></a>'État

Le type d’État sur lequel la `folder` fonction opère, par exemple, accepte comme premier argument et retourne.
### <a name="t"></a>Peut

Type des `array` éléments.