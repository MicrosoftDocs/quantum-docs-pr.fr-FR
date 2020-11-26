---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209857"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI fonction)

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Déplace la représentation au niveau du bit d’un nombre laissé par un nombre donné de bits.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Nombre dont la représentation au niveau du bit doit être décalée vers la gauche (plus significative).


### <a name="amount--int"></a>montant : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits par lequel doit `value` être décalé vers la gauche.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Valeur de `value` , décalée vers la gauche par `amount` bits.

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```