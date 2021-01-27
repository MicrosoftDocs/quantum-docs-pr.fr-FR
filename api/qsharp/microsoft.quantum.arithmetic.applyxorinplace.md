---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Opération ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843475"
---
# <a name="applyxorinplace-operation"></a>Opération ApplyXorInPlace

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération XOR au niveau du bit entre un entier classique et un entier représenté par un registre de qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Applique des `X` opérations à qubits dans un registre Little endian basé sur 1 bits dans un entier.

Faites-nous part `value` d’un et laissez y être un entier non signé encodé dans `target` , puis `InPlaceXorLE` effectue une opération donnée par le mappage suivant : $ \ket{y}\rightarrow \ket{y\oplus a} $, où $ \oplus $ est l’opérateur de bits or exclusif.

## <a name="input"></a>Entrée

### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Entier qui est supposé être non négatif.


### <a name="target--littleendian"></a>cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique utilisé pour stocker `value` l’encodage Little endian.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

