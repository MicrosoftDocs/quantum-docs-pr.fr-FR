---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193010"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="4b8f7-102">DiscreteUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="4b8f7-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4b8f7-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4b8f7-105">Retourne une distribution uniforme sur une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="4b8f7-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="4b8f7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4b8f7-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="4b8f7-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b8f7-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="4b8f7-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="4b8f7-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b8f7-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="4b8f7-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="4b8f7-111">Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="4b8f7-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="4b8f7-112">Une distribution dont les variates aléatoires sont des entiers dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="4b8f7-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b8f7-113">Notes</span><span class="sxs-lookup"><span data-stu-id="4b8f7-113">Remarks</span></span>

<span data-ttu-id="4b8f7-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="4b8f7-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b8f7-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b8f7-115">See Also</span></span>

- [<span data-ttu-id="4b8f7-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="4b8f7-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)