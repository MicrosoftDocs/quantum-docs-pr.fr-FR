---
uid: Microsoft.Quantum.Measurement.MResetX
title: Opération MResetX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194200"
---
# <a name="mresetx-operation"></a>Opération MResetX

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mesure un qubit unique dans la base X et le réinitialise à un état initial fixe à la suite de la mesure.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Description

Effectue une mesure de qubit unique dans le $X $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.

## <a name="input"></a>Entrée

### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit unique à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Résultat de la mesure `target` dans le Pauli $X $.