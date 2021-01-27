---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Opération EncodeIntoBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826673"
---
# <a name="encodeintobitflipcode-operation"></a>Opération EncodeIntoBitFlipCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Encode le code [3, 1, 3]/⟦ 3, 1, 1 ⟧.

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrée

### <a name="physregister--qubit"></a>physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits physique représentant les données à protéger.


### <a name="auxqubits--qubit"></a>auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre des qubits auxiliaires initialement dans l’État $ \ket {00} $ à utiliser pour l’encodage des données à protéger.



## <a name="output--logicalregister"></a>Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Qubits physique et auxiliaire utilisés dans l’encodage, représentés sous la forme d’un registre logique.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)