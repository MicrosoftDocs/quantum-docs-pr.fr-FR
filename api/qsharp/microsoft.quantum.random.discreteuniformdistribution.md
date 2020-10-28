---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706726"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="99bdc-102">DiscreteUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="99bdc-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="99bdc-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="99bdc-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="99bdc-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99bdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99bdc-105">Retourne une distribution uniforme sur une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="99bdc-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="99bdc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="99bdc-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="99bdc-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99bdc-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99bdc-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="99bdc-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="99bdc-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99bdc-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99bdc-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="99bdc-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="99bdc-111">Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="99bdc-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="99bdc-112">Une distribution dont les variates aléatoires sont des entiers dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="99bdc-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="99bdc-113">Notes</span><span class="sxs-lookup"><span data-stu-id="99bdc-113">Remarks</span></span>

<span data-ttu-id="99bdc-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="99bdc-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="99bdc-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99bdc-115">See Also</span></span>

- [<span data-ttu-id="99bdc-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="99bdc-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)