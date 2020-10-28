---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701473"
---
# <a name="greaterthani-function"></a>GreaterThanI fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


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