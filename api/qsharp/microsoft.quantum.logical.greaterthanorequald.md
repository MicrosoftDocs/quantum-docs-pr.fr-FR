---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702070"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="f4b29-102">GreaterThanOrEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="f4b29-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="f4b29-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4b29-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4b29-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4b29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4b29-105">Retourne la valeur true si et seulement si un nombre est supérieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="f4b29-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f4b29-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f4b29-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f4b29-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4b29-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4b29-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="f4b29-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f4b29-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4b29-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4b29-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="f4b29-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4b29-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4b29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4b29-112">`true` Si et seulement si `a` est supérieur à ou est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="f4b29-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b29-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f4b29-113">Remarks</span></span>

<span data-ttu-id="f4b29-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="f4b29-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```