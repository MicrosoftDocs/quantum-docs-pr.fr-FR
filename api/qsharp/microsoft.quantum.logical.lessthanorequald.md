---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197634"
---
# <a name="lessthanorequald-function"></a>LessThanOrEqualD fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--double"></a>r : [double](xref:microsoft.quantum.lang-ref.double)

Première valeur à comparer.


### <a name="b--double"></a>b : [double](xref:microsoft.quantum.lang-ref.double)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est inférieur ou égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```