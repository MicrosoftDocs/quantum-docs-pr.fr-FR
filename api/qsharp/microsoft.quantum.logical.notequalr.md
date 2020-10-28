---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701392"
---
# <a name="notequalr-function"></a>NotEqualR fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


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