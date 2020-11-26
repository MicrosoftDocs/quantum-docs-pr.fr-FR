---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUAL, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198161"
---
# <a name="equali-function"></a>EQUAL, fonction

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées sont égales.

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

Première valeur à comparer.


### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et uniquement si `a` est égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```