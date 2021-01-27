---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848489"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="df648-102">NotNearlyEqualD fonction)</span><span class="sxs-lookup"><span data-stu-id="df648-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="df648-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="df648-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="df648-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df648-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df648-105">Retourne true si et seulement si deux entrées ne sont pas presque égales (autrement dit, qu’elles ne sont pas comprises dans une tolérance de 1e-12).</span><span class="sxs-lookup"><span data-stu-id="df648-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="df648-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="df648-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="df648-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df648-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df648-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="df648-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="df648-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df648-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df648-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="df648-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="df648-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df648-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df648-112">`true` Si et seulement si `a` n’est pas presque égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="df648-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="df648-113">Notes</span><span class="sxs-lookup"><span data-stu-id="df648-113">Remarks</span></span>

<span data-ttu-id="df648-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="df648-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```