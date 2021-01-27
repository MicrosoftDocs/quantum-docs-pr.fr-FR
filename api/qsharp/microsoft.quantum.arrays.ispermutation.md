---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848093"
---
# <a name="ispermutation-function"></a>IsPermutation fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Génère la valeur true si et seulement si un tableau donné représente une permutation.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Description

Pour un tableau `array` de longueur donné `n` , retourne true si et seulement si chaque entier de `0` à `n - 1` apparaît exactement une fois dans `array` , ce qui `array` peut être interprété comme une permutation sur les `n` éléments.

## <a name="input"></a>Entrée

### <a name="permuation--int"></a>permuation : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau qui peut ou ne peut pas représenter une permutation.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="example"></a>Exemple

Le code Q # suivant imprime le message « tous les diagnostics ont été effectués avec succès » :

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Notes

Un tableau de longueur zéro est une permutation.