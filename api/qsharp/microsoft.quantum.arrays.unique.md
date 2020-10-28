---
uid: Microsoft.Quantum.Arrays.Unique
title: Fonction unique
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705718"
---
# <a name="unique-function"></a>Fonction unique

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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