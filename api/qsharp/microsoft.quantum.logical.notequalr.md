---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197192"
---
# <a name="notequalr-function"></a><span data-ttu-id="1d490-102">NotEqualR fonction)</span><span class="sxs-lookup"><span data-stu-id="1d490-102">NotEqualR function</span></span>

<span data-ttu-id="1d490-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1d490-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1d490-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d490-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d490-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="1d490-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="1d490-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1d490-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="1d490-107">r : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="1d490-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="1d490-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="1d490-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="1d490-109">b : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="1d490-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="1d490-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="1d490-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1d490-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1d490-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1d490-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="1d490-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d490-113">Notes</span><span class="sxs-lookup"><span data-stu-id="1d490-113">Remarks</span></span>

<span data-ttu-id="1d490-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="1d490-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```