---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Fonction énumérée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221417"
---
# <a name="enumerated-function"></a>Fonction énumérée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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