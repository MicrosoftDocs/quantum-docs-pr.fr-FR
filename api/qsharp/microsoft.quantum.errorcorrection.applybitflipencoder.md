---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Opération ApplyBitFlipEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827693"
---
# <a name="applybitflipencoder-operation"></a>Opération ApplyBitFlipEncoder

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération privée utilisée pour implémenter à la fois le codeur et le décodeur de retournement de bits.

Notez que cet encodeur peut utiliser la récupération cohérente sur place, auquel cas il « provoquera » l’erreur décrite par l’état initial de `auxQubits` .
En particulier, si `auxQubits` est initialement dans l’État $ \ket {10} $, cela provoque une erreur $X _ 1 $ sur le qubit encodé.

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="coherentrecovery--bool"></a>coherentRecovery : [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- doi : 10.1103/PhysRevA. 85.044302