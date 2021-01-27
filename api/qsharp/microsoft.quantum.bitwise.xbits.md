---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845242"
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