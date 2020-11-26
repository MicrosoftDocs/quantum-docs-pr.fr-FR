---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230529"
---
# <a name="intstopaulis-function"></a>IntsToPaulis fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit un tableau d’entiers en un tableau d’opérateurs Pauli qubit uniques.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrée

### <a name="ints--int"></a>ints : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’entiers dans la plage `0..3`  à convertir en opérateurs Pauli.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau `paulis` d’opérateurs Pauli de `Pauli[]` la même longueur que celui `ints` qui `paulis[idxPauli]` est égal à l’élément de `[PauliI, PauliX, PauliY, PauliZ]` donné par `ints[idxPauli]` .