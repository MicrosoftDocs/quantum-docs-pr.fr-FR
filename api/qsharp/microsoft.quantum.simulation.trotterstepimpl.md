---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Opération TrotterStepImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: bc6c3c6656da319fce9c7c48824dbc4ad75ccc83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203413"
---
# <a name="trotterstepimpl-operation"></a>Opération TrotterStepImpl

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémente l’évolution du temps d’un terme contenu dans un `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Description complète du système à simuler.


### <a name="idx--int"></a>idx : [int](xref:microsoft.quantum.lang-ref.int)

Index entier vers un terme dans le système décrit.


### <a name="stepsize--double"></a>procédure : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur sur la durée de l’heure-évolution par terme indexée par `idx` .


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits traité par la simulation.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

