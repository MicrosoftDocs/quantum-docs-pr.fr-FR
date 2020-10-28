---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708531"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="25025-102">ExtendedGreatestCommonDivisorI fonction)</span><span class="sxs-lookup"><span data-stu-id="25025-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="25025-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="25025-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="25025-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25025-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25025-105">Calcule un tuple $ (u, v) $ de sorte que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, où $ \operatorname{GCD} $ est $a le plus grand diviseur commun de $a $ et $b $.</span><span class="sxs-lookup"><span data-stu-id="25025-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="25025-106">Le GCD est toujours positif.</span><span class="sxs-lookup"><span data-stu-id="25025-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="25025-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="25025-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="25025-108">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25025-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25025-109">premier nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="25025-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="25025-110">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25025-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25025-111">deuxième nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="25025-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="25025-112">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="25025-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="25025-113">Tuple $ (u, v) $ avec la propriété $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="25025-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="25025-114">Références</span><span class="sxs-lookup"><span data-stu-id="25025-114">References</span></span>

- <span data-ttu-id="25025-115">Cette implémentation est conforme à https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="25025-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>