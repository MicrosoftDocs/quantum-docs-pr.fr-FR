---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Opération IncrementPhaseByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843147"
---
# <a name="incrementphasebyinteger-operation"></a>Opération IncrementPhaseByInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Supposons que `target` encode un entier non signé $x $ dans un encodage Little endian et qu' `increment` il est égal à $a $.
Ensuite, cette opération implémente l’unité $ \ket{x} \mapsto \ket{x + a} $, où l’ajout est effectué modulo $2 ^ n $, où $n = \texttt{Length (target !)} $.

## <a name="input"></a>Entrée

### <a name="increment--int"></a>incrément : [entier](xref:microsoft.quantum.lang-ref.int)

Entier par lequel `target` est incrémenté.


### <a name="target--phaselittleendian"></a>cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Un registre Quantum encodant un entier non signé utilisant l’encodage Little-endian dans la base double (QFT).



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Notez que nous avons simplifié le circuit, car l’incrément est une constante classique, et non un registre Quantum.

Reportez-vous à la figure à la [ page 6 de arXiv : quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) pour le schéma du circuit et l’explication.

## <a name="references"></a>Références

- [*Thomas G. Draper*, arXiv : quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)