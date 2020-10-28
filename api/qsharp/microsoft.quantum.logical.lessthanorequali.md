---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701452"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="5ad54-102">LessThanOrEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="5ad54-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="5ad54-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5ad54-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5ad54-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ad54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ad54-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="5ad54-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5ad54-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5ad54-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5ad54-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ad54-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ad54-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="5ad54-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5ad54-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ad54-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ad54-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="5ad54-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5ad54-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ad54-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ad54-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="5ad54-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ad54-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5ad54-113">Remarks</span></span>

<span data-ttu-id="5ad54-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="5ad54-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```