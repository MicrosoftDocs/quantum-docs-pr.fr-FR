---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708069"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="935ee-102">GreaterThanOrEqualL fonction)</span><span class="sxs-lookup"><span data-stu-id="935ee-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="935ee-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="935ee-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="935ee-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="935ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="935ee-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="935ee-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="935ee-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="935ee-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="935ee-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="935ee-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="935ee-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="935ee-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="935ee-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="935ee-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="935ee-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="935ee-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="935ee-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="935ee-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="935ee-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="935ee-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="935ee-113">Notes</span><span class="sxs-lookup"><span data-stu-id="935ee-113">Remarks</span></span>

<span data-ttu-id="935ee-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="935ee-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```