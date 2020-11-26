---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Opération MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194132"
---
# <a name="mresetz-operation"></a>Opération MResetZ

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mesure un qubit unique dans la base Z et le réinitialise à un état initial fixe à la suite de la mesure.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Description

Effectue une mesure de qubit unique dans le $Z $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.

## <a name="input"></a>Entrée

### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit unique à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Résultat de la mesure `target` dans le Pauli $Z $.