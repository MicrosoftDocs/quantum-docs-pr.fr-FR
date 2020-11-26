---
uid: Microsoft.Quantum.Logical.EqualR
title: Fonction equaler
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198004"
---
# <a name="equalr-function"></a><span data-ttu-id="90006-102">Fonction equaler</span><span class="sxs-lookup"><span data-stu-id="90006-102">EqualR function</span></span>

<span data-ttu-id="90006-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="90006-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="90006-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90006-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90006-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="90006-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="90006-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="90006-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="90006-107">r : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="90006-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="90006-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="90006-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="90006-109">b : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="90006-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="90006-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="90006-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="90006-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90006-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90006-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="90006-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="90006-113">Notes</span><span class="sxs-lookup"><span data-stu-id="90006-113">Remarks</span></span>

<span data-ttu-id="90006-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="90006-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```