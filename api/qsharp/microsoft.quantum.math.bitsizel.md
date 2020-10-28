---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708303"
---
# <a name="bitsizel-function"></a><span data-ttu-id="e1776-102">BitSizeL fonction)</span><span class="sxs-lookup"><span data-stu-id="e1776-102">BitSizeL function</span></span>

<span data-ttu-id="e1776-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e1776-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e1776-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1776-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1776-105">Pour un entier non négatif `a` , retourne le nombre de bits requis pour représenter `a` .</span><span class="sxs-lookup"><span data-stu-id="e1776-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="e1776-106">Autrement dit, retourne le plus petit $n $, ce qui $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="e1776-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="e1776-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e1776-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e1776-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e1776-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e1776-109">Entier dont la taille de bits doit être calculée.</span><span class="sxs-lookup"><span data-stu-id="e1776-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="e1776-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1776-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1776-111">Taille de bit de `a` .</span><span class="sxs-lookup"><span data-stu-id="e1776-111">The bit-size of `a`.</span></span>