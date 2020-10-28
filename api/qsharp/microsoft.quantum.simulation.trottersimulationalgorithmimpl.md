---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Opération TrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709233"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="955fd-102">Opération TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="955fd-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="955fd-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="955fd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="955fd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="955fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="955fd-105">Effectue des appels répétés à `TrotterStep` pour rapprocher l’opérateur Time-Evolution exp ( _-iHt_ ).</span><span class="sxs-lookup"><span data-stu-id="955fd-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="955fd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="955fd-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="955fd-107">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="955fd-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="955fd-108">Durée de l’évolution de l’heure simulée dans une seule étape trotter.</span><span class="sxs-lookup"><span data-stu-id="955fd-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="955fd-109">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="955fd-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="955fd-110">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="955fd-110">Order of Trotter integrator.</span></span> <span data-ttu-id="955fd-111">Il doit s’agir de 1 ou d’un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="955fd-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="955fd-112">maxTime : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="955fd-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="955fd-113">Durée totale de la simulation $t $.</span><span class="sxs-lookup"><span data-stu-id="955fd-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="955fd-114">evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="955fd-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="955fd-115">Description complète du système à simuler.</span><span class="sxs-lookup"><span data-stu-id="955fd-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="955fd-116">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="955fd-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="955fd-117">Qubits traité par la simulation.</span><span class="sxs-lookup"><span data-stu-id="955fd-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="955fd-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="955fd-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

