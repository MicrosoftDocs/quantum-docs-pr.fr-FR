---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701461"
---
# <a name="lessthanl-function"></a><span data-ttu-id="c9693-102">LessThanL fonction)</span><span class="sxs-lookup"><span data-stu-id="c9693-102">LessThanL function</span></span>

<span data-ttu-id="c9693-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c9693-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c9693-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9693-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9693-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="c9693-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c9693-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c9693-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c9693-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c9693-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c9693-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c9693-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c9693-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c9693-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c9693-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c9693-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c9693-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c9693-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c9693-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="c9693-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9693-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c9693-113">Remarks</span></span>

<span data-ttu-id="c9693-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c9693-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```