---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220829"
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