---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Opération IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707270"
---
# <a name="incrementbyinteger-operation"></a>Opération IncrementByInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

