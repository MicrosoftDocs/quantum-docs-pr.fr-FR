---
uid: Microsoft.Quantum.Logical.EqualD
title: Equaled, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198144"
---
# <a name="equald-function"></a>Equaled, fonction

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées sont égales.

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--double"></a>r : [double](xref:microsoft.quantum.lang-ref.double)

Première valeur à comparer.


### <a name="b--double"></a>b : [double](xref:microsoft.quantum.lang-ref.double)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et uniquement si `a` est égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```