---
uid: Microsoft.Quantum.Arrays.Padded
title: Fonction rembourrée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845564"
---
# <a name="padded-function"></a>Fonction rembourrée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un tableau rempli à l’aide des valeurs spécifiées jusqu’à une longueur spécifiée.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="nelementstotal--int"></a>nElementsTotal : [entier](xref:microsoft.quantum.lang-ref.int)

Longueur du tableau rempli. Si ce est positif, `inputArray` est rempli à l’en-tête. Si ce est négatif, `inputArray` est rempli à la fin.


### <a name="defaultelement--t"></a>defaultElement : 't

Valeur par défaut à utiliser pour les éléments de remplissage.


### <a name="inputarray--t"></a>inputArray : 't []

Tableau dont les valeurs sont situées à l’en-tête du tableau de sortie.



## <a name="output--t"></a>Sortie : 't []

Tableau `output` qui est le `inputArray` remplissage de l’en-tête avec `defaultElement` s jusqu’à ce que `output` ait une longueur `nElementsTotal`

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau.

## <a name="example"></a>Exemple

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```