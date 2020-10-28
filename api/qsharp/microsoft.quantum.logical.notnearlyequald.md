---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707014"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="c5548-102">NotNearlyEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="c5548-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="c5548-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c5548-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c5548-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5548-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5548-105">Retourne true si et seulement si deux entrées ne sont pas presque égales (autrement dit, qu’elles ne sont pas comprises dans une tolérance de 1e-12).</span><span class="sxs-lookup"><span data-stu-id="c5548-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c5548-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c5548-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c5548-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5548-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5548-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c5548-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c5548-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5548-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5548-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c5548-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c5548-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5548-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5548-112">`true` Si et seulement si `a` n’est pas presque égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="c5548-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5548-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c5548-113">Remarks</span></span>

<span data-ttu-id="c5548-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c5548-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```