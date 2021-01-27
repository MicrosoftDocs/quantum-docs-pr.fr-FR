---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 048f91411099d24f3c0c5fd8ae3703779e7ab8a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847913"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="b1fcd-102">PauliStringFromGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="b1fcd-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="b1fcd-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b1fcd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b1fcd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1fcd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1fcd-105">Extrait la chaîne Pauli et ses index qubit d’un terme Pauli décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="b1fcd-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="b1fcd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b1fcd-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="b1fcd-107">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b1fcd-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b1fcd-108">`GeneratorIndex` type qui encode un terme Pauli.</span><span class="sxs-lookup"><span data-stu-id="b1fcd-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="b1fcd-109">Sortie : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="b1fcd-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="b1fcd-110">La chaîne Pauli du terme décrit par un `GeneratorIndex` , et les index du qubits sur lequel il agit.</span><span class="sxs-lookup"><span data-stu-id="b1fcd-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>