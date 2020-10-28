---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Opération EncodeIntoSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702505"
---
# <a name="encodeintosteanecode-operation"></a>Opération EncodeIntoSteaneCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


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