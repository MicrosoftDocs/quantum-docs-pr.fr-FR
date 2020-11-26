---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195506"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="4f76d-102">GreatestCommonDivisorL fonction)</span><span class="sxs-lookup"><span data-stu-id="4f76d-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="4f76d-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4f76d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4f76d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f76d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f76d-105">Calcule le plus grand commun diviseur de $a $ et $b $.</span><span class="sxs-lookup"><span data-stu-id="4f76d-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="4f76d-106">Le GCD est toujours positif.</span><span class="sxs-lookup"><span data-stu-id="4f76d-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="4f76d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4f76d-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4f76d-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f76d-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f76d-109">premier nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="4f76d-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4f76d-110">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f76d-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f76d-111">deuxième nombre duquel le plus grand commun diviseur est calculé</span><span class="sxs-lookup"><span data-stu-id="4f76d-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="4f76d-112">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f76d-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f76d-113">Plus grand commun diviseur de $a $ et $b $</span><span class="sxs-lookup"><span data-stu-id="4f76d-113">Greatest common divisor of $a$ and $b$</span></span>