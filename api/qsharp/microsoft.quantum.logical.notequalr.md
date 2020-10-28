---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701392"
---
# <a name="notequalr-function"></a><span data-ttu-id="3d707-102">NotEqualR fonction)</span><span class="sxs-lookup"><span data-stu-id="3d707-102">NotEqualR function</span></span>

<span data-ttu-id="3d707-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3d707-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3d707-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d707-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d707-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="3d707-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3d707-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3d707-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="3d707-107">r : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="3d707-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="3d707-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3d707-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="3d707-109">b : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="3d707-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="3d707-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3d707-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3d707-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3d707-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3d707-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="3d707-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d707-113">Notes</span><span class="sxs-lookup"><span data-stu-id="3d707-113">Remarks</span></span>

<span data-ttu-id="3d707-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="3d707-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```