---
uid: Microsoft.Quantum.Logical.EqualL
title: Fonction EQUAL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701497"
---
# <a name="equall-function"></a><span data-ttu-id="31449-102">Fonction EQUAL</span><span class="sxs-lookup"><span data-stu-id="31449-102">EqualL function</span></span>

<span data-ttu-id="31449-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="31449-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="31449-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31449-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31449-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="31449-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="31449-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="31449-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="31449-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31449-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31449-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="31449-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="31449-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31449-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31449-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="31449-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="31449-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31449-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31449-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="31449-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="31449-113">Notes</span><span class="sxs-lookup"><span data-stu-id="31449-113">Remarks</span></span>

<span data-ttu-id="31449-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="31449-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```