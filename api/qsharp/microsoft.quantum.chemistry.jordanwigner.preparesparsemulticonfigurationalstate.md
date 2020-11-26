---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Opération PrepareSparseMultiConfigurationalState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 4d39be70c48ed49a1eec410ed6f8e5081dc1e8ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224766"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a>Opération PrepareSparseMultiConfigurationalState

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


La préparation de l’état d’évaluation de l’État multi-configuration est partiellement allouée par l’ajout d’une version d’évaluation initiale.

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="initialstatepreparation--qubit--unit"></a>initialStatePreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Unité pour préparer l’état initial de l’essai.


### <a name="excitations--jordanwignerinputstate"></a>excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

Indique l’état initial de l’essai représenté par l’amplitude de l’excitation et les index qubit sur lesquels l’excitation agit.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de Hamilton.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

