---
uid: Microsoft.Quantum.Logical.EqualD
title: Equaled, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198144"
---
# <a name="equald-function"></a><span data-ttu-id="0913a-102">Equaled, fonction</span><span class="sxs-lookup"><span data-stu-id="0913a-102">EqualD function</span></span>

<span data-ttu-id="0913a-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0913a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0913a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0913a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0913a-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="0913a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0913a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0913a-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="0913a-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0913a-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0913a-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="0913a-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="0913a-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0913a-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0913a-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="0913a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0913a-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0913a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0913a-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="0913a-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0913a-113">Notes</span><span class="sxs-lookup"><span data-stu-id="0913a-113">Remarks</span></span>

<span data-ttu-id="0913a-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="0913a-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```