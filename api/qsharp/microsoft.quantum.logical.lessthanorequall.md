---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849112"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="eda64-102">LessThanOrEqualL fonction)</span><span class="sxs-lookup"><span data-stu-id="eda64-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="eda64-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eda64-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eda64-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eda64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eda64-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="eda64-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="eda64-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="eda64-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="eda64-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eda64-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eda64-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="eda64-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="eda64-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eda64-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eda64-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="eda64-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eda64-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eda64-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eda64-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="eda64-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eda64-113">Notes</span><span class="sxs-lookup"><span data-stu-id="eda64-113">Remarks</span></span>

<span data-ttu-id="eda64-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="eda64-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```