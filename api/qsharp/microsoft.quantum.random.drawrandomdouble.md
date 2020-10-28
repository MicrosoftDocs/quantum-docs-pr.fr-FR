---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708645"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="c06a8-102">Opération DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c06a8-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="c06a8-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c06a8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c06a8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c06a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c06a8-105">Dessine un nombre réel aléatoire dans un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="c06a8-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="c06a8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c06a8-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="c06a8-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06a8-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06a8-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="c06a8-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="c06a8-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06a8-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06a8-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="c06a8-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="c06a8-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06a8-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06a8-112">Nombre réel aléatoire dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="c06a8-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c06a8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c06a8-113">Remarks</span></span>

<span data-ttu-id="c06a8-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c06a8-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c06a8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c06a8-115">See Also</span></span>

- [<span data-ttu-id="c06a8-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="c06a8-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)