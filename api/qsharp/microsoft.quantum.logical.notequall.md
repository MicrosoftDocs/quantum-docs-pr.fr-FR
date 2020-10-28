---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701398"
---
# <a name="notequall-function"></a><span data-ttu-id="2919a-102">NotEqualL fonction)</span><span class="sxs-lookup"><span data-stu-id="2919a-102">NotEqualL function</span></span>

<span data-ttu-id="2919a-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2919a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2919a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2919a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2919a-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="2919a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2919a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2919a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2919a-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2919a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2919a-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2919a-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2919a-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2919a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2919a-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2919a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2919a-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2919a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2919a-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="2919a-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2919a-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2919a-113">Remarks</span></span>

<span data-ttu-id="2919a-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="2919a-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```