---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701239"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="ae97c-102">InterpolateGeneratorSystemsImpl fonction)</span><span class="sxs-lookup"><span data-stu-id="ae97c-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="ae97c-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ae97c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ae97c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae97c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae97c-105">Interpole de manière linéaire entre deux `GeneratorSystems` en fonction d’un paramètre de planification `s` compris entre 0 et 1 (inclus).</span><span class="sxs-lookup"><span data-stu-id="ae97c-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ae97c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ae97c-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="ae97c-107">planification : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae97c-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae97c-108">Un paramètre de planification $s \Dans [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="ae97c-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="ae97c-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ae97c-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ae97c-110">Début `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="ae97c-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="ae97c-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ae97c-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ae97c-112">Fin `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="ae97c-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="ae97c-113">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ae97c-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ae97c-114">`GeneratorSystem`Représentant un système qui est la somme des systèmes de générateur d’entrée, avec la pondération $ (1-s) $ on `generatorSystemStart` et le poids $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="ae97c-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae97c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae97c-115">See Also</span></span>

- [<span data-ttu-id="ae97c-116">Microsoft. Quantum. simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="ae97c-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)