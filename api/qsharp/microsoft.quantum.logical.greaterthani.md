---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701473"
---
# <a name="greaterthani-function"></a><span data-ttu-id="a2be0-102">GreaterThanI fonction)</span><span class="sxs-lookup"><span data-stu-id="a2be0-102">GreaterThanI function</span></span>

<span data-ttu-id="a2be0-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a2be0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a2be0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2be0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2be0-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="a2be0-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a2be0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a2be0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a2be0-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2be0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2be0-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="a2be0-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a2be0-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2be0-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2be0-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="a2be0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a2be0-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a2be0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a2be0-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="a2be0-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2be0-113">Notes</span><span class="sxs-lookup"><span data-stu-id="a2be0-113">Remarks</span></span>

<span data-ttu-id="a2be0-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="a2be0-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```