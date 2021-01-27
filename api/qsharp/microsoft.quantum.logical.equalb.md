---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817252"
---
# <a name="equalb-function"></a><span data-ttu-id="dbd21-102">EqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="dbd21-102">EqualB function</span></span>

<span data-ttu-id="dbd21-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dbd21-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dbd21-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbd21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbd21-105">Retourne la valeur true si et seulement si deux entrées sont égales.</span><span class="sxs-lookup"><span data-stu-id="dbd21-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="dbd21-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dbd21-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="dbd21-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbd21-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbd21-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dbd21-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="dbd21-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbd21-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbd21-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="dbd21-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dbd21-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbd21-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbd21-112">`true` Si et uniquement si `a` est égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="dbd21-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbd21-113">Notes</span><span class="sxs-lookup"><span data-stu-id="dbd21-113">Remarks</span></span>

<span data-ttu-id="dbd21-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="dbd21-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```