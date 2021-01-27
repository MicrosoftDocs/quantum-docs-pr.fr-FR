---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Opération SteaneCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 81abe75e2a315fe9a994147242f3c8c9bde586ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824722"
---
# <a name="steanecodeencoderimpl-operation"></a>Opération SteaneCodeEncoderImpl

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur du code Steane.

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="data--qubit"></a>données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 1 qubit qui est le qubit d’entrée.


### <a name="scratch--qubit"></a>Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 6 qubits qui ajoutent une redondance.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

