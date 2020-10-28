---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708435"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="c6e7f-102">GreaterThanOrEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="c6e7f-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c6e7f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6e7f-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="c6e7f-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c6e7f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c6e7f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c6e7f-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6e7f-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c6e7f-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c6e7f-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6e7f-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c6e7f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c6e7f-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c6e7f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c6e7f-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="c6e7f-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6e7f-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c6e7f-113">Remarks</span></span>

<span data-ttu-id="c6e7f-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c6e7f-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```