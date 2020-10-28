---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708528"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="3f1c3-102">ExtendedGreatestCommonDivisorL fonction)</span><span class="sxs-lookup"><span data-stu-id="3f1c3-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="3f1c3-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3f1c3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3f1c3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f1c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f1c3-105">Calcule un tuple $ (u, v) $ de sorte que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, où $ \operatorname{GCD} $ est $a le plus grand diviseur commun de $a $ et $b $.</span><span class="sxs-lookup"><span data-stu-id="3f1c3-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="3f1c3-106">Le GCD est toujours positif.</span><span class="sxs-lookup"><span data-stu-id="3f1c3-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="3f1c3-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3f1c3-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="3f1c3-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3f1c3-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3f1c3-109">premier nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="3f1c3-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="3f1c3-110">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3f1c3-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3f1c3-111">deuxième nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="3f1c3-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="3f1c3-112">Sortie : ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="3f1c3-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="3f1c3-113">Tuple $ (u, v) $ avec la propriété $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="3f1c3-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="3f1c3-114">Références</span><span class="sxs-lookup"><span data-stu-id="3f1c3-114">References</span></span>

- <span data-ttu-id="3f1c3-115">Cette implémentation est conforme à https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="3f1c3-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>