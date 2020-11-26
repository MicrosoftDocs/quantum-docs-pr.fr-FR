---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197564"
---
# <a name="lessthanorequali-function"></a>LessThanOrEqualI fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

Première valeur à comparer.


### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est inférieur ou égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```