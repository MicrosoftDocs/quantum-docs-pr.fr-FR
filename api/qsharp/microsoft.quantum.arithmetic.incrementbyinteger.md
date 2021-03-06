---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Opération IncrementByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843166"
---
# <a name="incrementbyinteger-operation"></a>Opération IncrementByInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Supposons que `target` encode un entier non signé $x $ dans un encodage Little endian et qu' `increment` il est égal à $a $.
Ensuite, cette opération implémente l’unité $ \ket{x} \mapsto \ket{x + a} $, où l’ajout est effectué modulo $2 ^ n $, où $n = \texttt{Length (target !)} $.

## <a name="input"></a>Entrée

### <a name="increment--int"></a>incrément : [entier](xref:microsoft.quantum.lang-ref.int)

Entier par lequel `target` est incrémenté.


### <a name="target--littleendian"></a>cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registre Quantum codant un entier non signé utilisant l’encodage Little endian.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

