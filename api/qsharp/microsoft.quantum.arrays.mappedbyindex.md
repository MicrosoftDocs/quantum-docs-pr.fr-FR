---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209925"
---
# <a name="mappedbyindex-function"></a>MappedByIndex fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau et d’une fonction définis pour les éléments indexés du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrée

### <a name="mapper--intt---u"></a>mappeur : ([int](xref:microsoft.quantum.lang-ref.int), 't)-> 'U

Fonction de `(Int, 'T)` à `'U` qui est utilisée pour mapper des éléments et leurs index.


### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments sur `'T` .



## <a name="output--u"></a>Sortie : 'U []

Tableau `'U[]` d’éléments mappés par la `mapper` fonction.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.
### <a name="u"></a>'U

Type de résultat de la `mapper` fonction.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. mapped](xref:Microsoft.Quantum.Arrays.Mapped)