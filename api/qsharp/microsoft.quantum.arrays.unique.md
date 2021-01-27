---
uid: Microsoft.Quantum.Arrays.Unique
title: Fonction unique
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850921"
---
# <a name="unique-function"></a>Fonction unique

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un nouveau tableau qui n’a pas d’éléments adjacents égaux.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Description

À partir d’un tableau d’éléments et d’une fonction pour tester l’égalité, cette fonction retourne un nouveau tableau dans lequel l’ordre relatif des éléments est conservé, mais tous les éléments adjacents qui sont égaux sont filtrés simplement en un seul élément.

## <a name="input"></a>Entrée

### <a name="equal--tt---bool"></a>égal à : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Fonction qui compare deux éléments de sorte qu' `a` il est considéré comme égal à `b` si `equal(a, b)` est `true` .


### <a name="array--t"></a>Tableau : 't []

Tableau à filtrer pour les éléments uniques.



## <a name="output--t"></a>Sortie : 't []

Tableau sans éléments adjacents égaux.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de chaque élément de `array` .

## <a name="example"></a>Exemple

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Notes

Si plusieurs éléments sont égaux, mais pas à côté, il y aura plusieurs occurrences dans le tableau de sortie.  Utilisez cette fonction conjointement avec `Sorted` pour récupérer un tableau avec des éléments uniques globaux.