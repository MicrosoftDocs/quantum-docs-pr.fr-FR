---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197379"
---
# <a name="notequalb-function"></a><span data-ttu-id="0e1d8-102">NotEqualB fonction)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-102">NotEqualB function</span></span>

<span data-ttu-id="0e1d8-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0e1d8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e1d8-105">Retourne la valeur true si et seulement si deux entrées ne sont pas égales.</span><span class="sxs-lookup"><span data-stu-id="0e1d8-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="0e1d8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0e1d8-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0e1d8-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0e1d8-108">Première valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="0e1d8-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="0e1d8-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0e1d8-110">Deuxième valeur à comparer.</span><span class="sxs-lookup"><span data-stu-id="0e1d8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0e1d8-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0e1d8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0e1d8-112">`true` Si et seulement si `a` n’est pas égal à `b` .</span><span class="sxs-lookup"><span data-stu-id="0e1d8-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e1d8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="0e1d8-113">Remarks</span></span>

<span data-ttu-id="0e1d8-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="0e1d8-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```