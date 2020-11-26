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
# <a name="intstopaulis-function"></a><span data-ttu-id="8d24e-102">IntsToPaulis fonction)</span><span class="sxs-lookup"><span data-stu-id="8d24e-102">IntsToPaulis function</span></span>

<span data-ttu-id="8d24e-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8d24e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8d24e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d24e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d24e-105">Convertit un tableau d’entiers en un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="8d24e-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="8d24e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8d24e-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="8d24e-107">ints : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d24e-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d24e-108">Tableau d’entiers dans la plage `0..3`  à convertir en opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="8d24e-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8d24e-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8d24e-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8d24e-110">Tableau `paulis` d’opérateurs Pauli de `Pauli[]` la même longueur que celui `ints` qui `paulis[idxPauli]` est égal à l’élément de `[PauliI, PauliX, PauliY, PauliZ]` donné par `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="8d24e-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>