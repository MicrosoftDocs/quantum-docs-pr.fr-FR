---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849174"
---
# <a name="lessthand-function"></a><span data-ttu-id="c68cd-102">LessThanD fonction)</span><span class="sxs-lookup"><span data-stu-id="c68cd-102">LessThanD function</span></span>

<span data-ttu-id="c68cd-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c68cd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c68cd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c68cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c68cd-105">Retourne la valeur true si et seulement si un nombre est inférieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="c68cd-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c68cd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c68cd-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c68cd-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c68cd-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c68cd-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c68cd-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c68cd-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c68cd-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c68cd-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c68cd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c68cd-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c68cd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c68cd-112">`true` Si et seulement si `a` est strictement inférieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="c68cd-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c68cd-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c68cd-113">Remarks</span></span>

<span data-ttu-id="c68cd-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c68cd-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```