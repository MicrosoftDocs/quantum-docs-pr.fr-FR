---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814421"
---
# <a name="notequalb-function"></a><span data-ttu-id="3699d-102">NotEqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="3699d-102">NotEqualB function</span></span>

<span data-ttu-id="3699d-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3699d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3699d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3699d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3699d-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="3699d-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="3699d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3699d-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="3699d-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3699d-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3699d-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3699d-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="3699d-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3699d-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3699d-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="3699d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3699d-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3699d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3699d-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="3699d-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3699d-113">Notes</span><span class="sxs-lookup"><span data-stu-id="3699d-113">Remarks</span></span>

<span data-ttu-id="3699d-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="3699d-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```