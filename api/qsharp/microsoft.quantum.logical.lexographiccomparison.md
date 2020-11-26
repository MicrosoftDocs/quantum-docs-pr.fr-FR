---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197582"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une fonction de comparaison, retourne une nouvelle fonction que lexographically compare deux tableaux.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Entrée

### <a name="elementcomparison--tt---bool"></a>elementComparison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction qui compare deux éléments `x` et `y` et retourne si `x` est inférieur ou égal à `y` .



## <a name="output--tt---bool"></a>Sortie : ('t [], 't [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction qui compare deux tableaux `xs` et `ys` et retourne si `xs` se produit avant ou égal à `ys` dans le classement lexographical.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments des tableaux comparés.

## <a name="remarks"></a>Notes

La comparaison lexographic entre deux tableaux `xs` et `ys` est définie par la procédure suivante. Nous disons que deux éléments `x` et `y` sont équivalents si `elementComparison(x, y)` et `elementComparison(y, x)` sont tous les deux vrais.

- Les deux tableaux sont comparés élément par élément jusqu’à la première paire d’éléments qui ne sont pas équivalents. Le tableau contenant l’élément qui se produit en premier en fonction de `elementComparison` est dit se produire en premier dans le classement lexographical.
- Si aucun élément inéquivalent n’est trouvé et que l’un des tableaux est plus long que l’autre, le tableau le plus petit est dit en premier.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. tri](xref:Microsoft.Quantum.Arrays.Sorted)