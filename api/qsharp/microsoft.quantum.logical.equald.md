---
uid: Microsoft.Quantum.Logical.EqualD
title: Equaled, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702079"
---
# <a name="equald-function"></a><span data-ttu-id="8c164-102">Equaled, fonction</span><span class="sxs-lookup"><span data-stu-id="8c164-102">EqualD function</span></span>

<span data-ttu-id="8c164-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8c164-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8c164-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c164-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c164-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="8c164-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="8c164-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8c164-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="8c164-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8c164-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8c164-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="8c164-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="8c164-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8c164-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8c164-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="8c164-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8c164-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8c164-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8c164-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="8c164-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c164-113">Notes</span><span class="sxs-lookup"><span data-stu-id="8c164-113">Remarks</span></span>

<span data-ttu-id="8c164-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="8c164-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```