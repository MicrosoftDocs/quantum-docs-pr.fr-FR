---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707051"
---
# <a name="equalb-function"></a><span data-ttu-id="2258a-102">EqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="2258a-102">EqualB function</span></span>

<span data-ttu-id="2258a-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2258a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2258a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2258a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2258a-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="2258a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="2258a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2258a-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="2258a-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2258a-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2258a-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2258a-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="2258a-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2258a-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2258a-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2258a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2258a-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2258a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2258a-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="2258a-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2258a-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2258a-113">Remarks</span></span>

<span data-ttu-id="2258a-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="2258a-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```