---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708888"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="c730f-102">GetGeneratorSystemFunction fonction)</span><span class="sxs-lookup"><span data-stu-id="c730f-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="c730f-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c730f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c730f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c730f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c730f-105">Récupère la `GeneratorIndex` fonction dans un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="c730f-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="c730f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c730f-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="c730f-107">generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c730f-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c730f-108">`GeneratorSystem` présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="c730f-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="c730f-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c730f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c730f-110">Fonction qui indexe chaque `GeneratorIndex` terme dans un même sein.</span><span class="sxs-lookup"><span data-stu-id="c730f-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="c730f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c730f-111">See Also</span></span>

- [<span data-ttu-id="c730f-112">Microsoft. Quantum. simulation. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="c730f-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="c730f-113">Microsoft. Quantum. simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="c730f-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)