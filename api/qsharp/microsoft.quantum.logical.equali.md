---
uid: Microsoft.Quantum.Logical.EqualI
title: EQUAL, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816752"
---
# <a name="equali-function"></a><span data-ttu-id="f2da2-102">EQUAL, fonction</span><span class="sxs-lookup"><span data-stu-id="f2da2-102">EqualI function</span></span>

<span data-ttu-id="f2da2-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f2da2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f2da2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2da2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2da2-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="f2da2-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f2da2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f2da2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f2da2-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2da2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2da2-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="f2da2-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="f2da2-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2da2-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2da2-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="f2da2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f2da2-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f2da2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f2da2-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="f2da2-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2da2-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f2da2-113">Remarks</span></span>

<span data-ttu-id="f2da2-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="f2da2-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```