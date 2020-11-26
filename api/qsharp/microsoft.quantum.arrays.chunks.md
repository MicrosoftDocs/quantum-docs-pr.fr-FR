---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segments, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221604"
---
# <a name="chunks-function"></a><span data-ttu-id="d5517-102">Segments, fonction</span><span class="sxs-lookup"><span data-stu-id="d5517-102">Chunks function</span></span>

<span data-ttu-id="d5517-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d5517-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d5517-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5517-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5517-105">Fractionne un tableau en plusieurs parties de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="d5517-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="d5517-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d5517-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="d5517-107">nElements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5517-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5517-108">Longueur de chaque segment.</span><span class="sxs-lookup"><span data-stu-id="d5517-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="d5517-109">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="d5517-109">arr : 'T[]</span></span>

<span data-ttu-id="d5517-110">Tableau à fractionner.</span><span class="sxs-lookup"><span data-stu-id="d5517-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="d5517-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="d5517-111">Output : 'T[][]</span></span>

<span data-ttu-id="d5517-112">Tableau contenant chaque segment du tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="d5517-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d5517-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d5517-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5517-114">Peut</span><span class="sxs-lookup"><span data-stu-id="d5517-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d5517-115">Notes</span><span class="sxs-lookup"><span data-stu-id="d5517-115">Remarks</span></span>

<span data-ttu-id="d5517-116">Notez que le dernier élément de la sortie peut être plus petit que `nElements` si `Length(arr)` n’est pas divisible par `nElements` .</span><span class="sxs-lookup"><span data-stu-id="d5517-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>