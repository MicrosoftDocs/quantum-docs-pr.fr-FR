---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197991"
---
# <a name="greaterthani-function"></a><span data-ttu-id="ac7d1-102">GreaterThanI fonction)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-102">GreaterThanI function</span></span>

<span data-ttu-id="ac7d1-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ac7d1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac7d1-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="ac7d1-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ac7d1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ac7d1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ac7d1-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac7d1-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="ac7d1-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ac7d1-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac7d1-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="ac7d1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ac7d1-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ac7d1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ac7d1-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="ac7d1-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac7d1-113">Notes</span><span class="sxs-lookup"><span data-stu-id="ac7d1-113">Remarks</span></span>

<span data-ttu-id="ac7d1-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="ac7d1-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```