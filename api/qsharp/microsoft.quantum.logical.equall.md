---
uid: Microsoft.Quantum.Logical.EqualL
title: Fonction EQUAL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198110"
---
# <a name="equall-function"></a><span data-ttu-id="2cb29-102">Fonction EQUAL</span><span class="sxs-lookup"><span data-stu-id="2cb29-102">EqualL function</span></span>

<span data-ttu-id="2cb29-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2cb29-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2cb29-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cb29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cb29-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="2cb29-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2cb29-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2cb29-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2cb29-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2cb29-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2cb29-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2cb29-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2cb29-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2cb29-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2cb29-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="2cb29-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2cb29-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2cb29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2cb29-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="2cb29-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2cb29-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2cb29-113">Remarks</span></span>

<span data-ttu-id="2cb29-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="2cb29-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```