---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Opération DecodeFromSteaneCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 50fc6fb22e8b65ce10aba41e18362ad96236a907
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201136"
---
# <a name="decodefromsteanecode-operation"></a>Opération DecodeFromSteaneCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération d’encodage inverse qui mappe un registre quantique non encodé à un registre quantique encodé sous le code Quantum ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrée

### <a name="logicalregister--logicalregister"></a>logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tableau de qubits représentant l’état logique de code 5-qubit encodé.



## <a name="output--qubitqubit"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Tableau qubit de longueur 1 représentant l’état non encodé dans le premier paramètre, avec qubits auxiliaire dans le deuxième paramètre.

## <a name="remarks"></a>Notes

Le décodeur choisi utilise la propriété de code CSS du code Steane ⟦ 7, 1, 3 ⟧, c.-à-d., il corrige les erreurs X et Z séparément. Une propriété du code est que l’emplacement de la correction Z, respectivement, à appliquer est l’encodage 3 bits du X, respectivement, le syndrome Z lorsqu’il est considéré comme un entier.

## <a name="references"></a>Références

- D. Gottesman, « codes stabilisants et correction des erreurs Quantum », doctorat. thèse, Caltech, 1997 ; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)