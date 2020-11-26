---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197192"
---
# <a name="notequalr-function"></a>NotEqualR fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées ne sont pas égales.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--__invalidresult__"></a>r : __non <Result> valide__

Première valeur à comparer.


### <a name="b--__invalidresult__"></a>b : __non <Result> valide__

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` n’est pas égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```