---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Opération DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708933"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="2bb73-102">Opération DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="2bb73-102">DrawRandomInt operation</span></span>

<span data-ttu-id="2bb73-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2bb73-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2bb73-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bb73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bb73-105">Dessine un entier aléatoire dans une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="2bb73-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2bb73-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2bb73-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="2bb73-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb73-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb73-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="2bb73-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="2bb73-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb73-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb73-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="2bb73-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="2bb73-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb73-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb73-112">Entier dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="2bb73-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bb73-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2bb73-113">Remarks</span></span>

<span data-ttu-id="2bb73-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="2bb73-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bb73-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bb73-115">See Also</span></span>

- [<span data-ttu-id="2bb73-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="2bb73-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)