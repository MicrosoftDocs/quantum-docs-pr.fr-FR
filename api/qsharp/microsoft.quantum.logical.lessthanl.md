---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197719"
---
# <a name="lessthanl-function"></a><span data-ttu-id="24d86-102">LessThanL fonction)</span><span class="sxs-lookup"><span data-stu-id="24d86-102">LessThanL function</span></span>

<span data-ttu-id="24d86-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="24d86-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="24d86-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24d86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24d86-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="24d86-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="24d86-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="24d86-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="24d86-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="24d86-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="24d86-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="24d86-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="24d86-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="24d86-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="24d86-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="24d86-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="24d86-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="24d86-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="24d86-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="24d86-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="24d86-113">Notes</span><span class="sxs-lookup"><span data-stu-id="24d86-113">Remarks</span></span>

<span data-ttu-id="24d86-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="24d86-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```