---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197564"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="546de-102">LessThanOrEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="546de-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="546de-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="546de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="546de-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="546de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="546de-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="546de-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="546de-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="546de-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="546de-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="546de-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="546de-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="546de-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="546de-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="546de-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="546de-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="546de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="546de-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="546de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="546de-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="546de-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="546de-113">Notes</span><span class="sxs-lookup"><span data-stu-id="546de-113">Remarks</span></span>

<span data-ttu-id="546de-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="546de-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```