---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210061"
---
# <a name="constantarray-function"></a>ConstantArray fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="length--int"></a>Longueur : [int](xref:microsoft.quantum.lang-ref.int)

Longueur du nouveau tableau.


### <a name="value--t"></a>valeur : 't

Valeur de chaque élément du nouveau tableau.



## <a name="output--t"></a>Sortie : 't []

Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

