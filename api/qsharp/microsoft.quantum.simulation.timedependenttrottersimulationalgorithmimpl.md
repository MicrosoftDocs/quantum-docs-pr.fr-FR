---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: Opération TimeDependentTrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706435"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a>Opération TimeDependentTrotterSimulationAlgorithmImpl

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Implémentation de plusieurs étapes Trotter pour rapprocher un opérateur unitaire qui résout l’équation Schrödinger qui dépend du temps.

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="trotterstepsize--double"></a>trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)

Durée de l’évolution de l’heure simulée dans une seule étape trotter.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Ordre de l’intégrateur trotter. Il doit s’agir de 1 ou d’un nombre pair.


### <a name="maxtime--double"></a>maxTime : [double](xref:microsoft.quantum.lang-ref.double)

Durée totale de la simulation $t $.


### <a name="evolutionschedule--evolutionschedule"></a>evolutionSchedule : [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)

Description complète du système dépendant du temps à simuler.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits traité par la simulation.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

