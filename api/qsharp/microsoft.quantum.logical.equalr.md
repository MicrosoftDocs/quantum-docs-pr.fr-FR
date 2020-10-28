---
uid: Microsoft.Quantum.Logical.EqualR
title: Fonction equaler
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701494"
---
# <a name="equalr-function"></a><span data-ttu-id="3a8d9-102">Fonction equaler</span><span class="sxs-lookup"><span data-stu-id="3a8d9-102">EqualR function</span></span>

<span data-ttu-id="3a8d9-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3a8d9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3a8d9-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a8d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a8d9-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3a8d9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3a8d9-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="3a8d9-107">r : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="3a8d9-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="3a8d9-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="3a8d9-109">b : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="3a8d9-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="3a8d9-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3a8d9-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3a8d9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3a8d9-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="3a8d9-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a8d9-113">Notes</span><span class="sxs-lookup"><span data-stu-id="3a8d9-113">Remarks</span></span>

<span data-ttu-id="3a8d9-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="3a8d9-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```