---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197804"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="e8f6b-102">GreaterThanOrEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="e8f6b-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e8f6b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8f6b-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="e8f6b-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e8f6b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8f6b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e8f6b-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8f6b-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="e8f6b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e8f6b-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8f6b-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="e8f6b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e8f6b-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8f6b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e8f6b-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="e8f6b-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8f6b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e8f6b-113">Remarks</span></span>

<span data-ttu-id="e8f6b-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="e8f6b-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```