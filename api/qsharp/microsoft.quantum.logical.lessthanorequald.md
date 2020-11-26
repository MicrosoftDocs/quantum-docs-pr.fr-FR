---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197634"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="b6aed-102">LessThanOrEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="b6aed-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="b6aed-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b6aed-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b6aed-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6aed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6aed-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="b6aed-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b6aed-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b6aed-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b6aed-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6aed-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6aed-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="b6aed-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b6aed-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6aed-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6aed-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="b6aed-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b6aed-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b6aed-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b6aed-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="b6aed-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6aed-113">Notes</span><span class="sxs-lookup"><span data-stu-id="b6aed-113">Remarks</span></span>

<span data-ttu-id="b6aed-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="b6aed-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```