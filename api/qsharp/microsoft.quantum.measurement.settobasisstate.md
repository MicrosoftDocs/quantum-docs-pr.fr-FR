---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Opération SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708939"
---
# <a name="settobasisstate-operation"></a>Opération SetToBasisState

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Packages [](https://nuget.org/packages/)


Définit un qubit sur un état de base donné en mesurant le qubit et en appliquant un retournement binaire, si nécessaire.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="desired--__invalidresult__"></a>desired __: <Result> non valide__

État de base auquel le qubit doit être défini.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit dont l’État doit être défini.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Comme un invariant de cette opération, l’appel de `M(q)` juste après `SetToBasisState(result, q)` retourne `result` .