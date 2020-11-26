---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Opération MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227078"
---
# <a name="measureallz-operation"></a>Opération MeasureAllZ

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mesure conjointement un registre de qubits dans la base Z Pauli.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Description

Mesure un registre de qubits dans la $Z \otimes Z \otimes \cdots \otimes Z $, représentant la parité de l’intégralité du Registre.

## <a name="input"></a>Entrée

### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Résultat de la mesure de $Z \otimes Z \otimes \cdots \otimes Z $.