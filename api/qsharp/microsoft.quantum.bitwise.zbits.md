---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219445"
---
# <a name="zbits-function"></a>ZBits fonction)

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne un entier représentant les bits Z d’un tableau d’opérateurs Pauli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau d’opérateurs Pauli à représenter sous la forme d’un entier.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier $x $ avec la représentation binaire $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, où $p _i = $0 si `paulis[i]` est `PauliI` ou `PauliX` et où $p _i = $1 si `paulis[i]` est `PauliY` ou `PauliZ` .

## <a name="remarks"></a>Notes

La fonction lèvera une exception si la longueur du `paulis` tableau est supérieure à 63.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. bit. XBits](xref:Microsoft.Quantum.Bitwise.XBits)