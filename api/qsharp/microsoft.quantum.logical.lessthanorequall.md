---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701446"
---
# <a name="lessthanorequall-function"></a>LessThanOrEqualL fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Première valeur à comparer.


### <a name="b--bigint"></a>b : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est inférieur ou égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```