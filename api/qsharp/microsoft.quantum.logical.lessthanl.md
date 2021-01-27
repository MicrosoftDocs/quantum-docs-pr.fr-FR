---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849150"
---
# <a name="lessthanl-function"></a><span data-ttu-id="cc941-102">LessThanL fonction)</span><span class="sxs-lookup"><span data-stu-id="cc941-102">LessThanL function</span></span>

<span data-ttu-id="cc941-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc941-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc941-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc941-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc941-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="cc941-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cc941-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cc941-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cc941-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc941-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc941-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="cc941-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cc941-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc941-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc941-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="cc941-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc941-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc941-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc941-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="cc941-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc941-113">Notes</span><span class="sxs-lookup"><span data-stu-id="cc941-113">Remarks</span></span>

<span data-ttu-id="cc941-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="cc941-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```