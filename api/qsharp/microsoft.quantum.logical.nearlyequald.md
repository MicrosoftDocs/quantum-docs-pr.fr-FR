---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814370"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="496ac-102">NearlyEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="496ac-102">NearlyEqualD function</span></span>

<span data-ttu-id="496ac-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="496ac-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="496ac-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="496ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="496ac-105">Retourne true si et seulement si deux entrées sont presque égales (autrement dit, dans une tolérance de 1e-12).</span><span class="sxs-lookup"><span data-stu-id="496ac-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="496ac-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="496ac-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="496ac-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="496ac-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="496ac-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="496ac-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="496ac-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="496ac-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="496ac-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="496ac-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="496ac-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="496ac-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="496ac-112">`true` Si et seulement si `a` est presque égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="496ac-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="496ac-113">Notes</span><span class="sxs-lookup"><span data-stu-id="496ac-113">Remarks</span></span>

<span data-ttu-id="496ac-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="496ac-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```