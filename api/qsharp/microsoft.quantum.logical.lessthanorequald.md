---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701458"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="57724-102">LessThanOrEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="57724-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="57724-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="57724-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="57724-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57724-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57724-105">Retourne true si et seulement si un nombre est inférieur ou égal à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="57724-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="57724-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="57724-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="57724-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57724-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57724-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="57724-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="57724-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57724-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57724-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="57724-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="57724-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="57724-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="57724-112">`true` Si et seulement si `a` est inférieur ou égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="57724-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="57724-113">Notes</span><span class="sxs-lookup"><span data-stu-id="57724-113">Remarks</span></span>

<span data-ttu-id="57724-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="57724-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```