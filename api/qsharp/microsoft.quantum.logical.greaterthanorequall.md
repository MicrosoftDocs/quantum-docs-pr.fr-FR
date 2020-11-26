---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197753"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="02464-102">GreaterThanOrEqualL fonction)</span><span class="sxs-lookup"><span data-stu-id="02464-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="02464-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="02464-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="02464-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02464-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02464-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="02464-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="02464-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="02464-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="02464-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02464-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="02464-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="02464-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="02464-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02464-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="02464-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="02464-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="02464-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02464-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="02464-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="02464-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="02464-113">Notes</span><span class="sxs-lookup"><span data-stu-id="02464-113">Remarks</span></span>

<span data-ttu-id="02464-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="02464-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```