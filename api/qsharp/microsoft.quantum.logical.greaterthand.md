---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701482"
---
# <a name="greaterthand-function"></a><span data-ttu-id="c13c8-102">GreaterThanD fonction)</span><span class="sxs-lookup"><span data-stu-id="c13c8-102">GreaterThanD function</span></span>

<span data-ttu-id="c13c8-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c13c8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c13c8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c13c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c13c8-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="c13c8-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c13c8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c13c8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c13c8-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c13c8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c13c8-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c13c8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c13c8-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c13c8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c13c8-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="c13c8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c13c8-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c13c8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c13c8-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="c13c8-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c13c8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c13c8-113">Remarks</span></span>

<span data-ttu-id="c13c8-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c13c8-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```