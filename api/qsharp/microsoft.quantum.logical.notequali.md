---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701407"
---
# <a name="notequali-function"></a><span data-ttu-id="d6452-102">NotEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="d6452-102">NotEqualI function</span></span>

<span data-ttu-id="d6452-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d6452-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d6452-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6452-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6452-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="d6452-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="d6452-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d6452-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d6452-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6452-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6452-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="d6452-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="d6452-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6452-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6452-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="d6452-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d6452-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6452-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6452-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="d6452-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6452-113">Notes</span><span class="sxs-lookup"><span data-stu-id="d6452-113">Remarks</span></span>

<span data-ttu-id="d6452-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="d6452-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```