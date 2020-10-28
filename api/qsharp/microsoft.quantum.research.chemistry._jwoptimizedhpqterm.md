---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: Opération de _JWOptimizedHpqTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 503de03a379ac0ede3754aa7a31ac2ce84e5c675
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709026"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="e5af2-102">Opération de _JWOptimizedHpqTerm</span><span class="sxs-lookup"><span data-stu-id="e5af2-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="e5af2-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e5af2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="e5af2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5af2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5af2-105">Applique l’évolution de l’heure par un terme PQ décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e5af2-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e5af2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e5af2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e5af2-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e5af2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e5af2-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="e5af2-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e5af2-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5af2-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5af2-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="e5af2-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="e5af2-111">parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5af2-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5af2-112">Qubit qui détermine le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="e5af2-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e5af2-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e5af2-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e5af2-114">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="e5af2-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5af2-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5af2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

