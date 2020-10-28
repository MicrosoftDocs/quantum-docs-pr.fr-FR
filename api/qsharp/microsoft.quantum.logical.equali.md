---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUAL, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701503"
---
# <a name="equali-function"></a><span data-ttu-id="fdaa5-102">EQUAL, fonction</span><span class="sxs-lookup"><span data-stu-id="fdaa5-102">EqualI function</span></span>

<span data-ttu-id="fdaa5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fdaa5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fdaa5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdaa5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdaa5-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="fdaa5-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="fdaa5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fdaa5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fdaa5-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdaa5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdaa5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="fdaa5-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="fdaa5-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdaa5-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdaa5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="fdaa5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fdaa5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fdaa5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fdaa5-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="fdaa5-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdaa5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="fdaa5-113">Remarks</span></span>

<span data-ttu-id="fdaa5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="fdaa5-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```