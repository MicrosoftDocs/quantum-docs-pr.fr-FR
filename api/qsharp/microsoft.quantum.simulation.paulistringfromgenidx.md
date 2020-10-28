---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701713"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="c2e9c-102">PauliStringFromGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="c2e9c-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="c2e9c-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c2e9c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c2e9c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2e9c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2e9c-105">Extrait la chaîne Pauli et ses index qubit d’un terme Pauli décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c2e9c-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="c2e9c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c2e9c-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="c2e9c-107">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c2e9c-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c2e9c-108">`GeneratorIndex` type qui encode un terme Pauli.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="c2e9c-109">Sortie : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="c2e9c-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="c2e9c-110">La chaîne Pauli du terme décrit par un `GeneratorIndex` , et les index du qubits sur lequel il agit.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>