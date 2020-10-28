---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705899"
---
# <a name="mappedbyindex-function"></a>MappedByIndex fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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