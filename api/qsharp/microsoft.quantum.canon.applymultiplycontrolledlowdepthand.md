---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Opération ApplyMultiplyControlledLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209194"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>Opération ApplyMultiplyControlledLowDepthAnd

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémente une porte Toffoli à plusieurs contrôleurs, en supposant que la cible qubit est initialisée 0.  L’opération joint part du principe que le qubit cible sera réinitialisé à 0.  Requiert une profondeur de 1, tandis que le nombre de qubits d’assistance est exponentiel dans le nombre de qubits.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="controls--qubit"></a>contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de contrôle


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cible



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

