---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 332f9ea1753b539eba7b931d5b948b2a238d1abf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701425"
---
# <a name="nearlyequald-function"></a>NearlyEqualD fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


Retourne true si et seulement si deux entrées sont presque égales (autrement dit, dans une tolérance de 1e-12).

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--double"></a>r : [double](xref:microsoft.quantum.lang-ref.double)

Première valeur à comparer.


### <a name="b--double"></a>b : [double](xref:microsoft.quantum.lang-ref.double)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` est presque égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```