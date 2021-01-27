---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 26a963645758b6de83654304c38830af5c561b3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849220"
---
# <a name="greaterthand-function"></a><span data-ttu-id="ff4a5-102">GreaterThanD fonction)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-102">GreaterThanD function</span></span>

<span data-ttu-id="ff4a5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ff4a5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff4a5-105">Retourne la valeur true si et seulement si un nombre est supérieur à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="ff4a5-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ff4a5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ff4a5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ff4a5-107">r : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff4a5-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="ff4a5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ff4a5-109">b : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff4a5-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="ff4a5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ff4a5-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff4a5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff4a5-112">`true` Si et seulement si `a` est strictement supérieur à `b` .</span><span class="sxs-lookup"><span data-stu-id="ff4a5-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff4a5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="ff4a5-113">Remarks</span></span>

<span data-ttu-id="ff4a5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="ff4a5-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanD(a, b);
```