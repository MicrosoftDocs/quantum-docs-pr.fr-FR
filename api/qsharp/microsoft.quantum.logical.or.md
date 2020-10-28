---
uid: Microsoft.Quantum.Logical.Or
title: Fonction or
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706515"
---
# <a name="or-function"></a><span data-ttu-id="e060b-102">Fonction or</span><span class="sxs-lookup"><span data-stu-id="e060b-102">Or function</span></span>

<span data-ttu-id="e060b-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e060b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e060b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e060b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e060b-105">Retourne la disjonction booléenne de deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="e060b-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="e060b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e060b-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="e060b-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e060b-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e060b-108">Première valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="e060b-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="e060b-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e060b-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e060b-110">Deuxième valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="e060b-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e060b-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e060b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e060b-112">`true` Si et uniquement si `a` ou ont la valeur `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="e060b-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e060b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e060b-113">Remarks</span></span>

<span data-ttu-id="e060b-114">Contrairement `or` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.</span><span class="sxs-lookup"><span data-stu-id="e060b-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="e060b-115">Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="e060b-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```