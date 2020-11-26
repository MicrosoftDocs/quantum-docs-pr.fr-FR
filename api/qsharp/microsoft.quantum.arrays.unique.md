---
uid: Microsoft.Quantum.Arrays.Unique
title: Fonction unique
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220006"
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

## <a name="remarks"></a>Notes

Si plusieurs éléments sont égaux, mais pas à côté, il y aura plusieurs occurrences dans le tableau de sortie.  Utilisez cette fonction conjointement avec `Sorted` pour récupérer un tableau avec des éléments uniques globaux.