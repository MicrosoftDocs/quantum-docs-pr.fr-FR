---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197974"
---
# <a name="greaterthanl-function"></a>GreaterThanL fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Première valeur à comparer.


### <a name="b--bigint"></a>b : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est strictement supérieur à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```