---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Opération FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826081"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Opération FiveQubitCodeEncoderImpl

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur 5 qubit.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="data--qubit"></a>données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 1 qubit qui est le qubit d’entrée.


### <a name="scratch--qubit"></a>Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 4 qubits qui ajoutent une redondance.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’encodeur choisi a été prélevé sur le papier V. Kliuchnikov et D. Maslov, « optimisation des circuits Clifford », «phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) et requiert un total de 11 portes.