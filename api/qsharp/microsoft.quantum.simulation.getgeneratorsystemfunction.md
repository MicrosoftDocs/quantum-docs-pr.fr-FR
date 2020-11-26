---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 28e3c12d0ae0b08fc368c25eeb6f38d2834ca912
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229305"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="578f1-102">GetGeneratorSystemFunction fonction)</span><span class="sxs-lookup"><span data-stu-id="578f1-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="578f1-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="578f1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="578f1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="578f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="578f1-105">Récupère la `GeneratorIndex` fonction dans un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="578f1-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="578f1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="578f1-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="578f1-107">generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="578f1-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="578f1-108">`GeneratorSystem` présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="578f1-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="578f1-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="578f1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="578f1-110">Fonction qui indexe chaque `GeneratorIndex` terme dans un même sein.</span><span class="sxs-lookup"><span data-stu-id="578f1-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="578f1-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="578f1-111">See Also</span></span>

- [<span data-ttu-id="578f1-112">Microsoft. Quantum. simulation. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="578f1-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="578f1-113">Microsoft. Quantum. simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="578f1-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)