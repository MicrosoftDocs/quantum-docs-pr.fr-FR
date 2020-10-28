---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708426"
---
# <a name="notequald-function"></a><span data-ttu-id="86404-102">NotEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="86404-102">NotEqualD function</span></span>

<span data-ttu-id="86404-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="86404-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="86404-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86404-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86404-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="86404-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="86404-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="86404-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="86404-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="86404-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="86404-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="86404-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="86404-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="86404-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="86404-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="86404-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="86404-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="86404-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="86404-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="86404-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="86404-113">Notes</span><span class="sxs-lookup"><span data-stu-id="86404-113">Remarks</span></span>

<span data-ttu-id="86404-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="86404-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```