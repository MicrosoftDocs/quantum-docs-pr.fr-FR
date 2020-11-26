---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Opération DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192908"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="c144f-102">Opération DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="c144f-102">DrawRandomInt operation</span></span>

<span data-ttu-id="c144f-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c144f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c144f-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c144f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c144f-105">Dessine un entier aléatoire dans une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="c144f-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="c144f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c144f-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="c144f-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c144f-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c144f-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="c144f-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="c144f-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c144f-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c144f-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="c144f-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="c144f-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c144f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c144f-112">Entier dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="c144f-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c144f-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c144f-113">Remarks</span></span>

<span data-ttu-id="c144f-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c144f-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c144f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c144f-115">See Also</span></span>

- [<span data-ttu-id="c144f-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="c144f-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)