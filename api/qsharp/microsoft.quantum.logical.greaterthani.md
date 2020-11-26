---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197991"
---
# <a name="greaterthani-function"></a>GreaterThanI fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

Première valeur à comparer.


### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est strictement supérieur à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```