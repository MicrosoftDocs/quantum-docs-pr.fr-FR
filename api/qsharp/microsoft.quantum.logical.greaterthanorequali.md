---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197787"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="6e2c5-102">GreaterThanOrEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="6e2c5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6e2c5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e2c5-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="6e2c5-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6e2c5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6e2c5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6e2c5-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e2c5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="6e2c5-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6e2c5-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e2c5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="6e2c5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6e2c5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e2c5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e2c5-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="6e2c5-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e2c5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6e2c5-113">Remarks</span></span>

<span data-ttu-id="6e2c5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="6e2c5-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```