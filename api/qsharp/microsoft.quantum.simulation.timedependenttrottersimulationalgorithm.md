---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706443"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="a3955-102">TimeDependentTrotterSimulationAlgorithm fonction)</span><span class="sxs-lookup"><span data-stu-id="a3955-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="a3955-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a3955-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a3955-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3955-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3955-105">`TimeDependentSimulationAlgorithm` fonction qui utilise une décomposition Trotter – Suzuki pour rapprocher un opérateur unitaire qui résout l’équation Schrodinger qui dépend du temps.</span><span class="sxs-lookup"><span data-stu-id="a3955-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="a3955-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a3955-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="a3955-107">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3955-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3955-108">Durée de l’évolution de l’heure simulée dans une seule étape trotter.</span><span class="sxs-lookup"><span data-stu-id="a3955-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="a3955-109">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3955-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3955-110">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="a3955-110">Order of Trotter integrator.</span></span> <span data-ttu-id="a3955-111">Il doit s’agir de 1 ou d’un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="a3955-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="a3955-112">Sortie : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="a3955-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="a3955-113">Type `TimeDependentSimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="a3955-113">A `TimeDependentSimulationAlgorithm` type.</span></span>