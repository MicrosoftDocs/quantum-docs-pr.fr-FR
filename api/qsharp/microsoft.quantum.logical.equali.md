---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUAL, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198161"
---
# <a name="equali-function"></a><span data-ttu-id="34324-102">EQUAL, fonction</span><span class="sxs-lookup"><span data-stu-id="34324-102">EqualI function</span></span>

<span data-ttu-id="34324-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="34324-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="34324-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34324-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34324-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="34324-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="34324-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="34324-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="34324-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34324-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34324-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="34324-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="34324-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34324-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34324-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="34324-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="34324-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34324-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34324-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="34324-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="34324-113">Notes</span><span class="sxs-lookup"><span data-stu-id="34324-113">Remarks</span></span>

<span data-ttu-id="34324-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="34324-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```