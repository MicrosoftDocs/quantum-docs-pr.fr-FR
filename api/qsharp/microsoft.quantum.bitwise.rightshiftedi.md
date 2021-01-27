---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845253"
---
# <a name="rightshiftedi-function"></a>RightShiftedI fonction)

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).


### <a name="amount--int"></a>montant : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits par lequel doit `value` être décalé vers la droite.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Valeur de `value` , décalée vers la droite par `amount` bits.

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```