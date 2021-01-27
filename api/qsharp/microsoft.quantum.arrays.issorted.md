---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845739"
---
# <a name="issorted-function"></a>IsSorted fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau, retourne si ce tableau est trié comme défini par une fonction de comparaison donnée.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrée

### <a name="comparison--tt---bool"></a>Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction qui compare deux éléments de sorte que `a` est considéré comme inférieur ou égal à `b` si `comparison(a, b)` est `true` .


### <a name="array--t"></a>Tableau : 't []

Tableau à vérifier.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si pour chaque paire d’éléments `a` et `b` si `array` se produit dans cet ordre, `comparison(a, b)` est `true` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `array` .

## <a name="remarks"></a>Notes

La fonction `comparison` est supposée être transitive, de sorte que si `comparison(a, b)` et `comparison(b, c)` , `comparison(a, c)` est utilisé par défaut. Si cette propriété ne contient pas, la sortie de cette fonction est peut-être incorrecte.