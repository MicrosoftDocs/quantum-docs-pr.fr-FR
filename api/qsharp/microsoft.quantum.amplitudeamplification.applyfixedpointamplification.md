---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Opération ApplyFixedPointAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847231"
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