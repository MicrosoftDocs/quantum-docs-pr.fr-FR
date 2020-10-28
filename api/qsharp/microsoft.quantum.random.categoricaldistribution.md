---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708144"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="22ab1-102">CategoricalDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="22ab1-102">CategoricalDistribution function</span></span>

<span data-ttu-id="22ab1-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="22ab1-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="22ab1-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22ab1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22ab1-105">Retourne une distribution catégorique discrète, dans laquelle la probabilité pour chaque liste finie de résultats donnés est explicitement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="22ab1-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="22ab1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="22ab1-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="22ab1-107">sondes : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22ab1-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="22ab1-108">Probabilités pour chaque résultat de la distribution catégorique.</span><span class="sxs-lookup"><span data-stu-id="22ab1-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="22ab1-109">Ces probabilités ne peuvent pas être normalisées, mais elles doivent toutes être non négatives.</span><span class="sxs-lookup"><span data-stu-id="22ab1-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="22ab1-110">Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="22ab1-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="22ab1-111">Index `i` avec la probabilité `probs[i] / sum` , où `sum` est la somme de `probs` donnée par `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="22ab1-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>