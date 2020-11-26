---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: opération de _prepareTrialStateWrapper
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224681"
---
# <a name="_preparetrialstatewrapper-operation"></a>opération de _prepareTrialStateWrapper

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Wrapper privé autour de PrepareTrialState pour le rendre compatible avec EstimateFrequencyA en définissant un voisint.
EstimateFrequencyA dispose d’une fonctionnalité d’émulation intégrée lors du ciblage du QuantumSimulator, ce qui accélère son exécution.

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="inputstate--intjordanwignerinputstate"></a>inputState : ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])

L' Jordan-Wigner entrée nécessaire à l’exécution de PrepareTrialState.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre qubit.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

