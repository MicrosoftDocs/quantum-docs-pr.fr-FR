---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193078"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="e399f-102">ContinuousUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="e399f-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="e399f-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e399f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e399f-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e399f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e399f-105">Retourne une distribution uniforme sur un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="e399f-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="e399f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e399f-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="e399f-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e399f-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e399f-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="e399f-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="e399f-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e399f-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e399f-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="e399f-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="e399f-111">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="e399f-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="e399f-112">Distribution dont les variates aléatoires sont des nombres réels dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="e399f-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="e399f-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e399f-113">Remarks</span></span>

<span data-ttu-id="e399f-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="e399f-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e399f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e399f-115">See Also</span></span>

- [<span data-ttu-id="e399f-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="e399f-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)