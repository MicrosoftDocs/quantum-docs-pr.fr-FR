---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198467"
---
# <a name="equalb-function"></a><span data-ttu-id="5e6d5-102">EqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-102">EqualB function</span></span>

<span data-ttu-id="5e6d5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5e6d5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e6d5-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="5e6d5-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5e6d5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5e6d5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5e6d5-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e6d5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="5e6d5-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5e6d5-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e6d5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="5e6d5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5e6d5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e6d5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e6d5-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="5e6d5-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e6d5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5e6d5-113">Remarks</span></span>

<span data-ttu-id="5e6d5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="5e6d5-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```