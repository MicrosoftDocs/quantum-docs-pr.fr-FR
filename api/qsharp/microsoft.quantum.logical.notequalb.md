---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701410"
---
# <a name="notequalb-function"></a><span data-ttu-id="de8e5-102">NotEqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="de8e5-102">NotEqualB function</span></span>

<span data-ttu-id="de8e5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="de8e5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="de8e5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de8e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de8e5-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="de8e5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="de8e5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="de8e5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="de8e5-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de8e5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de8e5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="de8e5-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="de8e5-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de8e5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de8e5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="de8e5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="de8e5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de8e5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de8e5-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="de8e5-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="de8e5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="de8e5-113">Remarks</span></span>

<span data-ttu-id="de8e5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="de8e5-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```