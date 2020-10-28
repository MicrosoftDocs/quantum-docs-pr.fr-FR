---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705579"
---
# <a name="rightshiftedl-function"></a>RightShiftedL fonction)

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Packages [](https://nuget.org/packages/)


Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Entrée

### <a name="value--bigint"></a>valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).


### <a name="amount--int"></a>montant : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits par lequel doit `value` être décalé vers la droite.



## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valeur de `value` , décalée vers la droite par `amount` bits.

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```