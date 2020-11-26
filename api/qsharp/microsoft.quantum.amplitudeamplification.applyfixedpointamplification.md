---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Opération ApplyFixedPointAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191531"
---
# <a name="applyfixedpointamplification-operation"></a>Opération ApplyFixedPointAmplification

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Algorithme d’amplification d’amplitude Fixed-Point

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="statepreporacle--stateoracle"></a>statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Oracle unitaire qui prépare l’état de démarrage.


### <a name="startqubits--qubit"></a>startQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre qubit



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

StartQubits doit être dans l’État $ \ket{0 \cdots 0} $. Cette opération effectue une itération sur un certain nombre de requêtes dans les puissances de $2 $ jusqu’à ce qu’un nombre maximal de requêtes soit atteint ou que l’État cible soit trouvé.