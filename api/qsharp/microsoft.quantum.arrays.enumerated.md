---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Fonction énumérée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706067"
---
# <a name="enumerated-function"></a>Fonction énumérée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir d’un tableau, retourne un nouveau tableau contenant les éléments du tableau d’origine, ainsi que les index de chaque élément.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Entrée

### <a name="array--telement"></a>Tableau : 'TElement []

Tableau dont les éléments doivent être énumérés.



## <a name="output--inttelement"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int), 'TElement) []

Nouveau tableau contenant les éléments du tableau d’origine et leurs index.

## <a name="type-parameters"></a>Paramètres de type

### <a name="telement"></a>'TElement

Type des éléments du tableau.