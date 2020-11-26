---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195525"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="e2549-102">ExtendedGreatestCommonDivisorI fonction)</span><span class="sxs-lookup"><span data-stu-id="e2549-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="e2549-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e2549-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e2549-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2549-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2549-105">Calcule un tuple $ (u, v) $ de sorte que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, où $ \operatorname{GCD} $ est $a le plus grand diviseur commun de $a $ et $b $.</span><span class="sxs-lookup"><span data-stu-id="e2549-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="e2549-106">Le GCD est toujours positif.</span><span class="sxs-lookup"><span data-stu-id="e2549-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="e2549-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e2549-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e2549-108">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2549-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2549-109">premier nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="e2549-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="e2549-110">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2549-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2549-111">deuxième nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="e2549-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="e2549-112">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="e2549-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="e2549-113">Tuple $ (u, v) $ avec la propriété $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="e2549-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="e2549-114">Références</span><span class="sxs-lookup"><span data-stu-id="e2549-114">References</span></span>

- <span data-ttu-id="e2549-115">Cette implémentation est conforme à https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="e2549-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>