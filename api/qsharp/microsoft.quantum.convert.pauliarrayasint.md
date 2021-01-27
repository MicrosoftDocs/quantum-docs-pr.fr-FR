---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832709"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Encode un opérateur Pauli à plusieurs qubit représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques en un entier.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau d’au plus 31 opérateurs Pauli à qubit unique.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier qui identifie de manière unique `paulis` , comme décrit ci-dessous.

## <a name="remarks"></a>Notes

Chaque opérateur Pauli peut être encodé à l’aide de deux bits : $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

À partir d’un tableau d’opérateurs Pauli `[P0, ..., Pn]` , cette fonction retourne un entier avec une expansion binaire formée en concaténant les mappages de chaque opérateur Pauli dans l’ordre Big-endian `bits(Pn) ... bits(P0)` .