---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197209"
---
# <a name="notequali-function"></a><span data-ttu-id="dd066-102">NotEqualI fonction)</span><span class="sxs-lookup"><span data-stu-id="dd066-102">NotEqualI function</span></span>

<span data-ttu-id="dd066-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dd066-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dd066-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd066-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd066-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="dd066-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="dd066-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dd066-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd066-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd066-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd066-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dd066-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="dd066-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd066-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd066-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dd066-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dd066-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd066-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd066-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="dd066-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd066-113">Notes</span><span class="sxs-lookup"><span data-stu-id="dd066-113">Remarks</span></span>

<span data-ttu-id="dd066-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="dd066-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```