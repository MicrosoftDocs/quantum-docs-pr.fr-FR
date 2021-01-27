---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 9438fc05b4ccb041b087f9cfeb30ac0c8cfcabd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815609"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="32184-102">LessThanOrEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="32184-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="32184-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32184-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32184-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32184-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32184-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="32184-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="32184-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="32184-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="32184-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32184-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32184-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="32184-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="32184-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32184-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32184-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="32184-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32184-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32184-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32184-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="32184-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="32184-113">Notes</span><span class="sxs-lookup"><span data-stu-id="32184-113">Remarks</span></span>

<span data-ttu-id="32184-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="32184-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```