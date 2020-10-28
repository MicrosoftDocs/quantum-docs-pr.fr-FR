---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708429"
---
# <a name="lessthani-function"></a><span data-ttu-id="00fc5-102">LessThanI fonction)</span><span class="sxs-lookup"><span data-stu-id="00fc5-102">LessThanI function</span></span>

<span data-ttu-id="00fc5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="00fc5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="00fc5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00fc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00fc5-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="00fc5-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="00fc5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="00fc5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="00fc5-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00fc5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00fc5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="00fc5-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="00fc5-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00fc5-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00fc5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="00fc5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="00fc5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00fc5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00fc5-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="00fc5-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="00fc5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="00fc5-113">Remarks</span></span>

<span data-ttu-id="00fc5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="00fc5-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```