---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845667"
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

## <a name="example"></a>Exemple

Les deux lignes suivantes sont équivalentes :

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

and

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. mapped](xref:Microsoft.Quantum.Arrays.Mapped)