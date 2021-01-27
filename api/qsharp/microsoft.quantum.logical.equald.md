---
uid: Microsoft.Quantum.Logical.EqualD
title: Equaled, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816863"
---
# <a name="equald-function"></a><span data-ttu-id="31378-102">Equaled, fonction</span><span class="sxs-lookup"><span data-stu-id="31378-102">EqualD function</span></span>

<span data-ttu-id="31378-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="31378-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="31378-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31378-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31378-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="31378-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="31378-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="31378-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="31378-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="31378-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="31378-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="31378-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="31378-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="31378-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="31378-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="31378-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="31378-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31378-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31378-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="31378-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="31378-113">Notes</span><span class="sxs-lookup"><span data-stu-id="31378-113">Remarks</span></span>

<span data-ttu-id="31378-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="31378-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```