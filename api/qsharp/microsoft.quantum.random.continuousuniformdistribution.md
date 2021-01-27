---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842316"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="25581-102">ContinuousUniformDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="25581-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="25581-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="25581-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="25581-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="25581-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="25581-105">Retourne une distribution uniforme sur un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="25581-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="25581-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="25581-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="25581-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25581-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25581-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="25581-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="25581-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25581-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25581-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="25581-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="25581-111">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="25581-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="25581-112">Distribution dont les variates aléatoires sont des nombres réels dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="25581-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="25581-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="25581-113">Example</span></span>

<span data-ttu-id="25581-114">L’extrait de code Q # suivant dessine aléatoirement un angle entre $0 $ et $2 \pi $ :</span><span class="sxs-lookup"><span data-stu-id="25581-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="25581-115">Notes</span><span class="sxs-lookup"><span data-stu-id="25581-115">Remarks</span></span>

<span data-ttu-id="25581-116">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="25581-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="25581-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25581-117">See Also</span></span>

- [<span data-ttu-id="25581-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="25581-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)