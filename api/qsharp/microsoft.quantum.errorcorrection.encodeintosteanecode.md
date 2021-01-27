---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Opération EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826207"
---
# <a name="encodeintosteanecode-operation"></a>Opération EncodeIntoSteaneCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération d’encodage qui mappe un registre quantique non encodé à un registre quantique encodé sous le code Quantum ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrée

### <a name="physregister--qubit"></a>physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre qubit qui contient l’État Quantum non encodé


### <a name="auxqubits--qubit"></a>auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre qubit qui est initialement zéro et qui est ajouté au système Quantum pour permettre l’exécution d’une opération d’encodage



## <a name="output--logicalregister"></a>Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Registre quantique contenant l’état après l’application de l’encodeur Steane

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)