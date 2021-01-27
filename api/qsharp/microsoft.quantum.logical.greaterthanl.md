---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849198"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="eefbc-102">GreaterThanL fonction)</span><span class="sxs-lookup"><span data-stu-id="eefbc-102">GreaterThanL function</span></span>

<span data-ttu-id="eefbc-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eefbc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eefbc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eefbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eefbc-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="eefbc-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="eefbc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="eefbc-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="eefbc-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eefbc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eefbc-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="eefbc-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="eefbc-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eefbc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eefbc-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="eefbc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eefbc-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eefbc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eefbc-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="eefbc-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eefbc-113">Notes</span><span class="sxs-lookup"><span data-stu-id="eefbc-113">Remarks</span></span>

<span data-ttu-id="eefbc-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="eefbc-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```