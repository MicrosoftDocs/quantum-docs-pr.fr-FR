---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195849"
---
# <a name="bitsizei-function"></a><span data-ttu-id="c8a2b-102">BitSizeI fonction)</span><span class="sxs-lookup"><span data-stu-id="c8a2b-102">BitSizeI function</span></span>

<span data-ttu-id="c8a2b-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c8a2b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c8a2b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8a2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8a2b-105">Pour un entier non négatif `a` , retourne le nombre de bits requis pour représenter `a` .</span><span class="sxs-lookup"><span data-stu-id="c8a2b-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="c8a2b-106">Autrement dit, retourne le plus petit $n $, ce qui $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c8a2b-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="c8a2b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c8a2b-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c8a2b-108">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8a2b-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8a2b-109">Entier dont la taille de bits doit être calculée.</span><span class="sxs-lookup"><span data-stu-id="c8a2b-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="c8a2b-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8a2b-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8a2b-111">Taille de bit de `a` .</span><span class="sxs-lookup"><span data-stu-id="c8a2b-111">The bit-size of `a`.</span></span>