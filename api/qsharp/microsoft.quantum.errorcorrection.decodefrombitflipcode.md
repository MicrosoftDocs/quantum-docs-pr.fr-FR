---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Opération DecodeFromBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b16e84340053b6c1eab7b91ed8db0461b9eac98e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827559"
---
# <a name="decodefrombitflipcode-operation"></a>Opération DecodeFromBitFlipCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Décode à partir du code [3, 1, 3]/⟦ 3, 1, 1 ⟧.

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrée

### <a name="logicalregister--logicalregister"></a>logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Bloc de code du code d’inversion de bits.



## <a name="output--qubitqubit"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Tuple des données encodées dans le registre logique, et qubits auxiliaire utilisé pour représenter le syndrome.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. EncodeIntoBitFlipCode](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)