---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848909"
---
# <a name="bitsizel-function"></a><span data-ttu-id="4e23d-102">BitSizeL fonction)</span><span class="sxs-lookup"><span data-stu-id="4e23d-102">BitSizeL function</span></span>

<span data-ttu-id="4e23d-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4e23d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4e23d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e23d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e23d-105">Pour un entier non négatif `a` , retourne le nombre de bits requis pour représenter `a` .</span><span class="sxs-lookup"><span data-stu-id="4e23d-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="4e23d-106">Autrement dit, retourne le plus petit $n $, ce qui $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="4e23d-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="4e23d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4e23d-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4e23d-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4e23d-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4e23d-109">Entier dont la taille de bits doit être calculée.</span><span class="sxs-lookup"><span data-stu-id="4e23d-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="4e23d-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e23d-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e23d-111">Taille de bit de `a` .</span><span class="sxs-lookup"><span data-stu-id="4e23d-111">The bit-size of `a`.</span></span>