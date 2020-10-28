---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701446"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="3c113-102">LessThanOrEqualL fonction)</span><span class="sxs-lookup"><span data-stu-id="3c113-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="3c113-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3c113-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3c113-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c113-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c113-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="3c113-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="3c113-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c113-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="3c113-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3c113-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3c113-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3c113-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="3c113-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3c113-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3c113-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3c113-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3c113-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3c113-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3c113-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="3c113-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c113-113">Notes</span><span class="sxs-lookup"><span data-stu-id="3c113-113">Remarks</span></span>

<span data-ttu-id="3c113-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="3c113-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```