---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845654"
---
# <a name="mappedoverrange-function"></a>MappedOverRange fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour une plage et une fonction qui acceptent un entier comme entrée, retourne un nouveau tableau qui se compose des images des valeurs de plage sous la fonction.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="mapper--int---t"></a>mappeur : [int](xref:microsoft.quantum.lang-ref.int) -> 't

Fonction de `Int` à `'T` qui est utilisée pour mapper des valeurs de plage.


### <a name="range--range"></a>plage : [plage](xref:microsoft.quantum.lang-ref.range)

Plage d’entiers.



## <a name="output--t"></a>Sortie : 't []

Tableau `'T[]` d’éléments mappés par la `mapper` fonction.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de résultat de la `mapper` fonction.

## <a name="example"></a>Exemple

Cet exemple ajoute 1 à une plage de nombres pairs :

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, autrement dit, chaque fois que nous avons une fonction, `mapper: Int -> 'T` nous pouvons mapper les valeurs de la plage et produire un tableau de type `'T[]` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. mapped](xref:Microsoft.Quantum.Arrays.Mapped)