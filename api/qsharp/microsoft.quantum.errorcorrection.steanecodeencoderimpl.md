---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Opération SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702418"
---
# <a name="steanecodeencoderimpl-operation"></a>Opération SteaneCodeEncoderImpl

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur du code Steane.

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="data--qubit"></a>données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 1 qubit qui est le qubit d’entrée.


### <a name="scratch--qubit"></a>Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

tableau contenant 6 qubits qui ajoutent une redondance.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

