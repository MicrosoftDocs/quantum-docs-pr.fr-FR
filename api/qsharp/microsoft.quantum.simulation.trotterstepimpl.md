---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Opération TrotterStepImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709218"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="878e0-102">Opération TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="878e0-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="878e0-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="878e0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="878e0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="878e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="878e0-105">Implémente l’évolution du temps d’un terme contenu dans un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="878e0-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="878e0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="878e0-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="878e0-107">evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="878e0-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="878e0-108">Description complète du système à simuler.</span><span class="sxs-lookup"><span data-stu-id="878e0-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="878e0-109">idx : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="878e0-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="878e0-110">Index entier vers un terme dans le système décrit.</span><span class="sxs-lookup"><span data-stu-id="878e0-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="878e0-111">procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="878e0-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="878e0-112">Multiplicateur sur la durée de l’heure-évolution par terme indexée par `idx` .</span><span class="sxs-lookup"><span data-stu-id="878e0-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="878e0-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="878e0-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="878e0-114">Qubits traité par la simulation.</span><span class="sxs-lookup"><span data-stu-id="878e0-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="878e0-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="878e0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

