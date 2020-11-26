---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Opération TrotterSimulationAlgorithmImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203397"
---
# <a name="trottersimulationalgorithmimpl-operation"></a>Opération TrotterSimulationAlgorithmImpl

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Effectue des appels répétés à `TrotterStep` pour rapprocher l’opérateur Time-Evolution exp (_-iHt_).

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="trotterstepsize--double"></a>trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)

Durée de l’évolution de l’heure simulée dans une seule étape trotter.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Ordre de l’intégrateur trotter. Il doit s’agir de 1 ou d’un nombre pair.


### <a name="maxtime--double"></a>maxTime : [double](xref:microsoft.quantum.lang-ref.double)

Durée totale de la simulation $t $.


### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Description complète du système à simuler.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits traité par la simulation.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

