---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705891"
---
# <a name="mappedoverrange-function"></a>MappedOverRange fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Notes

La fonction est définie pour les types génériques, autrement dit, chaque fois que nous avons une fonction, `mapper: Int -> 'T` nous pouvons mapper les valeurs de la plage et produire un tableau de type `'T[]` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. mapped](xref:Microsoft.Quantum.Arrays.Mapped)