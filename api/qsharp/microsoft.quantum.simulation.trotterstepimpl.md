---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Opération TrotterStepImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709218"
---
# <a name="trotterstepimpl-operation"></a>Opération TrotterStepImpl

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Implémente l’évolution du temps d’un terme contenu dans un `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
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

