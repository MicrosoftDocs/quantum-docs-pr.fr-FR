---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701245"
---
# <a name="intstopaulis-function"></a>IntsToPaulis fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Convertit un tableau d’entiers en un tableau d’opérateurs Pauli qubit uniques.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrée

### <a name="ints--int"></a>ints : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’entiers dans la plage `0..3`  à convertir en opérateurs Pauli.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau `paulis` d’opérateurs Pauli de `Pauli[]` la même longueur que celui `ints` qui `paulis[idxPauli]` est égal à l’élément de `[PauliI, PauliX, PauliY, PauliZ]` donné par `ints[idxPauli]` .