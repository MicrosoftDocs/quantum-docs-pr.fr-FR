---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848604"
---
# <a name="fold-function"></a>Fold, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemple

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```