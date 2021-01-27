---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845306"
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

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```