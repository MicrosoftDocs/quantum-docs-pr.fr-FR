---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197770"
---
# <a name="lessthani-function"></a><span data-ttu-id="407ae-102">LessThanI fonction)</span><span class="sxs-lookup"><span data-stu-id="407ae-102">LessThanI function</span></span>

<span data-ttu-id="407ae-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="407ae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="407ae-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="407ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="407ae-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="407ae-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="407ae-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="407ae-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="407ae-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="407ae-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="407ae-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="407ae-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="407ae-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="407ae-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="407ae-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="407ae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="407ae-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="407ae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="407ae-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="407ae-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="407ae-113">Notes</span><span class="sxs-lookup"><span data-stu-id="407ae-113">Remarks</span></span>

<span data-ttu-id="407ae-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="407ae-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```