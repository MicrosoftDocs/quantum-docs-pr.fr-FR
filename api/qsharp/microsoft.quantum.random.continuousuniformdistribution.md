---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701236"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="f9472-102">ContinuousUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="f9472-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="f9472-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f9472-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f9472-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9472-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9472-105">Retourne une distribution uniforme sur un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="f9472-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="f9472-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f9472-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="f9472-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9472-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9472-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="f9472-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="f9472-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9472-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9472-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="f9472-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="f9472-111">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f9472-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f9472-112">Distribution dont les variates aléatoires sont des nombres réels dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="f9472-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9472-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f9472-113">Remarks</span></span>

<span data-ttu-id="f9472-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="f9472-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9472-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9472-115">See Also</span></span>

- [<span data-ttu-id="f9472-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="f9472-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)