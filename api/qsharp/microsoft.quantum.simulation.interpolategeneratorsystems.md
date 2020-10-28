---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701722"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="002a7-102">InterpolateGeneratorSystems fonction)</span><span class="sxs-lookup"><span data-stu-id="002a7-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="002a7-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="002a7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="002a7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="002a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="002a7-105">Retourne un `TimeDependentGeneratorSystem` qui représente l’interpolation linéaire entre deux `GeneratorSystem` s.</span><span class="sxs-lookup"><span data-stu-id="002a7-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="002a7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="002a7-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="002a7-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="002a7-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="002a7-108">Début `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="002a7-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="002a7-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="002a7-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="002a7-110">Fin `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="002a7-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="002a7-111">Sortie : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="002a7-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="002a7-112">`TimeDependentGeneratorSystem`Représentant un système qui est la somme des systèmes de générateur d’entrée, avec la pondération $ (1-s) $ on `generatorSystemStart` et le poids $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="002a7-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="002a7-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="002a7-113">See Also</span></span>

- [<span data-ttu-id="002a7-114">Microsoft. Quantum. simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="002a7-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="002a7-115">Microsoft. Quantum. simulation. TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="002a7-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)