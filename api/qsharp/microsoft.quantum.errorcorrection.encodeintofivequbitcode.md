---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Opération EncodeIntoFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826321"
---
# <a name="encodeintofivequbitcode-operation"></a>Opération EncodeIntoFiveQubitCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Encode le code Quantum ⟦ 5, 1, 3 ⟧.

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrée

### <a name="physregister--qubit"></a>physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit représentant un État non encodé. Ce tableau `Qubit[]` a une longueur de 1.


### <a name="auxqubits--qubit"></a>auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits auxiliaires qui sera utilisé pour représenter l’État encodé.



## <a name="output--logicalregister"></a>Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tableau de qubits physiques de type `LogicalRegister` qui stocke l’État encodé.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)