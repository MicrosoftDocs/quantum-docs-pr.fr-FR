---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701731"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="8bfbb-102">InterpolatedEvolution fonction)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="8bfbb-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8bfbb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bfbb-105">Effectue une interpolation entre deux générateurs avec une planification uniforme, en retournant une opération qui applique l’évolution simulée sous le générateur dépendant du temps à un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8bfbb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8bfbb-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="8bfbb-107">interpolationTime : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8bfbb-108">Temps nécessaire pour effectuer l’interpolation.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="8bfbb-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="8bfbb-110">Générateur initial pour simuler l’évolution sous.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="8bfbb-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="8bfbb-112">Générateur final pour simuler l’évolution.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="8bfbb-113">timeDependentSimulationAlgorithm : [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="8bfbb-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="8bfbb-114">Algorithme de simulation dépendant du temps qui sera utilisé pour simuler l’évolution pendant la planification de l’interpolation uniforme.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="8bfbb-115">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="8bfbb-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="8bfbb-116">Notes</span><span class="sxs-lookup"><span data-stu-id="8bfbb-116">Remarks</span></span>

<span data-ttu-id="8bfbb-117">Si le temps d’interpolation est choisi pour respecter les conditions adiabatic, cette fonction retourne une opération qui effectue la préparation de l’État adiabatic pour le générateur dynamique final.</span><span class="sxs-lookup"><span data-stu-id="8bfbb-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>