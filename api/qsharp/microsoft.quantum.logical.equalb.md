---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198467"
---
# <a name="equalb-function"></a>EqualB fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées sont égales.

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>r : [bool](xref:microsoft.quantum.lang-ref.bool)

Première valeur à comparer.


### <a name="b--bool"></a>b : [bool](xref:microsoft.quantum.lang-ref.bool)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et uniquement si `a` est égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```