---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708306"
---
# <a name="bitsizei-function"></a><span data-ttu-id="cd415-102">BitSizeI fonction)</span><span class="sxs-lookup"><span data-stu-id="cd415-102">BitSizeI function</span></span>

<span data-ttu-id="cd415-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cd415-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cd415-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd415-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd415-105">Pour un entier non négatif `a` , retourne le nombre de bits requis pour représenter `a` .</span><span class="sxs-lookup"><span data-stu-id="cd415-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="cd415-106">Autrement dit, retourne le plus petit $n $, ce qui $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="cd415-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="cd415-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="cd415-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="cd415-108">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd415-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd415-109">Entier dont la taille de bits doit être calculée.</span><span class="sxs-lookup"><span data-stu-id="cd415-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="cd415-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd415-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd415-111">Taille de bit de `a` .</span><span class="sxs-lookup"><span data-stu-id="cd415-111">The bit-size of `a`.</span></span>