---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709230"
---
# <a name="trotterstep-function"></a><span data-ttu-id="eed91-102">TrotterStep fonction)</span><span class="sxs-lookup"><span data-stu-id="eed91-102">TrotterStep function</span></span>

<span data-ttu-id="eed91-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="eed91-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="eed91-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eed91-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eed91-105">Implémente une seule heure-étape de l’évolution du temps par le système décrit dans `EvolutionGenerator` à l’aide d’une décomposition Trotter – Suzuki.</span><span class="sxs-lookup"><span data-stu-id="eed91-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="eed91-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="eed91-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="eed91-107">evolutionGenerator : [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="eed91-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="eed91-108">Description complète du système à simuler.</span><span class="sxs-lookup"><span data-stu-id="eed91-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="eed91-109">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eed91-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eed91-110">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="eed91-110">Order of Trotter integrator.</span></span> <span data-ttu-id="eed91-111">Il doit s’agir de 1 ou d’un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="eed91-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="eed91-112">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eed91-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eed91-113">Durée de l’évolution de l’heure simulée dans une seule étape trotter.</span><span class="sxs-lookup"><span data-stu-id="eed91-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="eed91-114">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="eed91-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="eed91-115">Opération unitaire qui correspond approximativement à une seule étape de l’évolution de l’heure pour la durée `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="eed91-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eed91-116">Notes</span><span class="sxs-lookup"><span data-stu-id="eed91-116">Remarks</span></span>

<span data-ttu-id="eed91-117">Pour plus d’informations sur la décomposition Trotter – Suzuki, consultez la section [composition chronologique](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="eed91-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>