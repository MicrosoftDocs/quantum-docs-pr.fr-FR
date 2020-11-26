---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: Opération de _JWOptimizedZTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 7c2ab2e7bbe628748dd4b6c022c4c96ad37ac314
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225820"
---
# <a name="_jwoptimizedzterm-operation"></a>Opération de _JWOptimizedZTerm

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Applique l’évolution de l’heure par un terme Z décrit par un `GeneratorIndex` .

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="term--generatorindex"></a>terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` représentant un terme Z.


### <a name="stepsize--double"></a>Procédure : [double](xref:microsoft.quantum.lang-ref.double)

Durée de l’évolution du temps.


### <a name="parityqubit--qubit"></a>parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit qui détermine le signe de l’évolution du temps.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de Hamilton.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

