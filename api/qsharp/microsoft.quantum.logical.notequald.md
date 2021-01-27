---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849047"
---
# <a name="notequald-function"></a><span data-ttu-id="b7d14-102">NotEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="b7d14-102">NotEqualD function</span></span>

<span data-ttu-id="b7d14-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b7d14-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b7d14-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7d14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7d14-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="b7d14-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b7d14-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b7d14-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b7d14-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7d14-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7d14-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="b7d14-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b7d14-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7d14-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7d14-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="b7d14-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b7d14-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b7d14-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b7d14-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="b7d14-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7d14-113">Notes</span><span class="sxs-lookup"><span data-stu-id="b7d14-113">Remarks</span></span>

<span data-ttu-id="b7d14-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="b7d14-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```