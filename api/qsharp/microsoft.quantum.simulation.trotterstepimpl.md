---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Opération TrotterStepImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: bc6c3c6656da319fce9c7c48824dbc4ad75ccc83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203413"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="794f9-102">Opération TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="794f9-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="794f9-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="794f9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="794f9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="794f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="794f9-105">Implémente l’évolution du temps d’un terme contenu dans un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="794f9-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="794f9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="794f9-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="794f9-107">evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="794f9-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="794f9-108">Description complète du système à simuler.</span><span class="sxs-lookup"><span data-stu-id="794f9-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="794f9-109">idx : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="794f9-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="794f9-110">Index entier vers un terme dans le système décrit.</span><span class="sxs-lookup"><span data-stu-id="794f9-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="794f9-111">procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="794f9-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="794f9-112">Multiplicateur sur la durée de l’heure-évolution par terme indexée par `idx` .</span><span class="sxs-lookup"><span data-stu-id="794f9-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="794f9-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="794f9-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="794f9-114">Qubits traité par la simulation.</span><span class="sxs-lookup"><span data-stu-id="794f9-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="794f9-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="794f9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

