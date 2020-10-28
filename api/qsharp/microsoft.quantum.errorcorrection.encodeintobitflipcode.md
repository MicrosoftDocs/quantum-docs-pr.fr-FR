---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Opération EncodeIntoBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702511"
---
# <a name="encodeintobitflipcode-operation"></a>Opération EncodeIntoBitFlipCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


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