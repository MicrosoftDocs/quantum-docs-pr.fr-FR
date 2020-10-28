---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706438"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="17b35-102">TrotterSimulationAlgorithm fonction)</span><span class="sxs-lookup"><span data-stu-id="17b35-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="17b35-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="17b35-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="17b35-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17b35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17b35-105">`SimulationAlgorithm` fonction qui utilise une décomposition Trotter – Suzuki pour rapprocher l’opérateur Time-Evolution _exp (-iHt)_ .</span><span class="sxs-lookup"><span data-stu-id="17b35-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="17b35-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="17b35-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="17b35-107">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17b35-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17b35-108">Durée de l’évolution de l’heure simulée dans une seule étape trotter.</span><span class="sxs-lookup"><span data-stu-id="17b35-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="17b35-109">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17b35-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17b35-110">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="17b35-110">Order of Trotter integrator.</span></span> <span data-ttu-id="17b35-111">Il doit s’agir de 1 ou d’un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="17b35-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="17b35-112">Sortie : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="17b35-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="17b35-113">Type `SimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="17b35-113">A `SimulationAlgorithm` type.</span></span>