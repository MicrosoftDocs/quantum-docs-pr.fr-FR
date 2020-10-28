---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701458"
---
# <a name="lessthanorequald-function"></a>LessThanOrEqualD fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


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