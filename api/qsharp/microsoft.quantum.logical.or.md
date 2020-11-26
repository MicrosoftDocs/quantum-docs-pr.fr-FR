---
uid: Microsoft.Quantum.Logical.Or
title: Fonction or
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197124"
---
# <a name="or-function"></a><span data-ttu-id="54082-102">Fonction or</span><span class="sxs-lookup"><span data-stu-id="54082-102">Or function</span></span>

<span data-ttu-id="54082-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="54082-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="54082-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54082-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54082-105">Retourne la disjonction booléenne de deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="54082-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="54082-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="54082-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="54082-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54082-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54082-108">Première valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="54082-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="54082-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54082-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54082-110">Deuxième valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="54082-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="54082-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54082-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54082-112">`true` Si et uniquement si `a` ou ont la valeur `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="54082-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="54082-113">Notes</span><span class="sxs-lookup"><span data-stu-id="54082-113">Remarks</span></span>

<span data-ttu-id="54082-114">Contrairement `or` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.</span><span class="sxs-lookup"><span data-stu-id="54082-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="54082-115">Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="54082-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```