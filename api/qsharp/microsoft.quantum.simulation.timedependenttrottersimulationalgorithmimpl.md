---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: Opération TimeDependentTrotterSimulationAlgorithmImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: 3a23c14e8181eeaf1614dab6f8aa5a002364c2b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847807"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="2574c-102">Opération TimeDependentTrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="2574c-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="2574c-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2574c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2574c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2574c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2574c-105">Implémentation de plusieurs étapes Trotter pour rapprocher un opérateur unitaire qui résout l’équation Schrödinger qui dépend du temps.</span><span class="sxs-lookup"><span data-stu-id="2574c-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2574c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2574c-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="2574c-107">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2574c-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2574c-108">Durée de l’évolution de l’heure simulée dans une seule étape trotter.</span><span class="sxs-lookup"><span data-stu-id="2574c-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2574c-109">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2574c-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2574c-110">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="2574c-110">Order of Trotter integrator.</span></span> <span data-ttu-id="2574c-111">Il doit s’agir de 1 ou d’un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="2574c-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="2574c-112">maxTime : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2574c-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2574c-113">Durée totale de la simulation $t $.</span><span class="sxs-lookup"><span data-stu-id="2574c-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="2574c-114">evolutionSchedule : [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="2574c-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="2574c-115">Description complète du système dépendant du temps à simuler.</span><span class="sxs-lookup"><span data-stu-id="2574c-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2574c-116">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2574c-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2574c-117">Qubits traité par la simulation.</span><span class="sxs-lookup"><span data-stu-id="2574c-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2574c-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2574c-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

