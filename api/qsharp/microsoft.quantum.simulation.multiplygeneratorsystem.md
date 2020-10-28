---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706686"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="08582-102">MultiplyGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="08582-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="08582-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="08582-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="08582-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08582-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08582-105">Multiplie le coefficient de tous les termes dans un `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="08582-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="08582-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="08582-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="08582-107">multiplicateur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08582-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08582-108">Multiplicateur sur le coefficient.</span><span class="sxs-lookup"><span data-stu-id="08582-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="08582-109">generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="08582-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="08582-110">`GeneratorSystem` à multiplier.</span><span class="sxs-lookup"><span data-stu-id="08582-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="08582-111">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="08582-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="08582-112">`GeneratorSystem`Représentant un système avec des coefficients d’un facteur `multiplier` plus grand.</span><span class="sxs-lookup"><span data-stu-id="08582-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="08582-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08582-113">See Also</span></span>

- [<span data-ttu-id="08582-114">Microsoft. Quantum. simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="08582-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)