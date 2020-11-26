---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209755"
---
# <a name="xbits-function"></a>XBits fonction)

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne un entier représentant les X bits d’un tableau d’opérateurs Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau d’opérateurs Pauli à représenter sous la forme d’un entier.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier $x $ avec la représentation binaire $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, où $p _i = $0 si `paulis[i]` est `PauliI` ou `PauliZ` et où $p _i = $1 si `paulis[i]` est `PauliX` ou `PauliY` .

## <a name="remarks"></a>Notes

La fonction lèvera une exception si la longueur du `paulis` tableau est supérieure à 63.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. bit. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)