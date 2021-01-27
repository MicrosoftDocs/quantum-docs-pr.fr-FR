---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853723"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="90125-102">DiscreteUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="90125-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="90125-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="90125-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="90125-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="90125-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="90125-105">Retourne une distribution uniforme sur une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="90125-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="90125-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="90125-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="90125-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90125-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90125-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="90125-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="90125-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90125-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90125-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="90125-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="90125-111">Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="90125-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="90125-112">Une distribution dont les variates aléatoires sont des entiers dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="90125-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="90125-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="90125-113">Example</span></span>

<span data-ttu-id="90125-114">L’extrait de code Q # suivant remplace de manière aléatoire un dé à six côtés :</span><span class="sxs-lookup"><span data-stu-id="90125-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="90125-115">Notes</span><span class="sxs-lookup"><span data-stu-id="90125-115">Remarks</span></span>

<span data-ttu-id="90125-116">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="90125-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="90125-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90125-117">See Also</span></span>

- [<span data-ttu-id="90125-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="90125-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)