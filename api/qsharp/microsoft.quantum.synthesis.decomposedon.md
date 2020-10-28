---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709173"
---
# <a name="decomposedon-function"></a><span data-ttu-id="1f9e2-102">DecomposedOn fonction)</span><span class="sxs-lookup"><span data-stu-id="1f9e2-102">DecomposedOn function</span></span>

<span data-ttu-id="1f9e2-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1f9e2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1f9e2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f9e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f9e2-105">Décompose une permutation sur une variable</span><span class="sxs-lookup"><span data-stu-id="1f9e2-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="1f9e2-106">Description</span><span class="sxs-lookup"><span data-stu-id="1f9e2-106">Description</span></span>

<span data-ttu-id="1f9e2-107">Étant donné une permutation $ \pi $ ( `perm` ) et un index $i $ ( `index` ), cette méthode retourne trois permutations $ ((\ pi_l, \ Pi_R), \pi') $, de telle sorte que les images de $ \ pi_l $ et $ \ Pi_R $ ne changent pas les bits dans leurs éléments aux index autres que $i $ et les images de $ \pi' $ ne changent pas le bit $i $ dans leurs éléments.</span><span class="sxs-lookup"><span data-stu-id="1f9e2-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="1f9e2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1f9e2-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="1f9e2-109">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f9e2-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="1f9e2-110">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f9e2-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="1f9e2-111">Sortie : (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="1f9e2-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

