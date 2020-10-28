---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Opération MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701932"
---
# <a name="mresetz-operation"></a>Opération MResetZ

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Packages [](https://nuget.org/packages/)


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