---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702073"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="dbffb-102">GreaterThanL fonction)</span><span class="sxs-lookup"><span data-stu-id="dbffb-102">GreaterThanL function</span></span>

<span data-ttu-id="dbffb-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dbffb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dbffb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbffb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbffb-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="dbffb-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="dbffb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dbffb-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="dbffb-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dbffb-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dbffb-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dbffb-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="dbffb-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dbffb-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dbffb-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dbffb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dbffb-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbffb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbffb-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="dbffb-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbffb-113">Notes</span><span class="sxs-lookup"><span data-stu-id="dbffb-113">Remarks</span></span>

<span data-ttu-id="dbffb-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="dbffb-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```