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
# <a name="intstopaulis-function"></a><span data-ttu-id="72594-102">IntsToPaulis fonction)</span><span class="sxs-lookup"><span data-stu-id="72594-102">IntsToPaulis function</span></span>

<span data-ttu-id="72594-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="72594-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="72594-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72594-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72594-105">Convertit un tableau d’entiers en un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="72594-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="72594-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="72594-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="72594-107">ints : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="72594-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="72594-108">Tableau d’entiers dans la plage `0..3`  à convertir en opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="72594-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="72594-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="72594-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="72594-110">Tableau `paulis` d’opérateurs Pauli de `Pauli[]` la même longueur que celui `ints` qui `paulis[idxPauli]` est égal à l’élément de `[PauliI, PauliX, PauliY, PauliZ]` donné par `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="72594-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>