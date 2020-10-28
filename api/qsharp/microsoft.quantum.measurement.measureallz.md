---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Opération MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701941"
---
# <a name="measureallz-operation"></a>Opération MeasureAllZ

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Packages [](https://nuget.org/packages/)


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