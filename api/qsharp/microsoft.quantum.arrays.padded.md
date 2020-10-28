---
uid: Microsoft.Quantum.Arrays.Padded
title: Fonction rembourrée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705851"
---
# <a name="padded-function"></a>Fonction rembourrée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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