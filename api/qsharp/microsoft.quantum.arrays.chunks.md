---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segments, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842877"
---
# <a name="chunks-function"></a><span data-ttu-id="3c34a-102">Segments, fonction</span><span class="sxs-lookup"><span data-stu-id="3c34a-102">Chunks function</span></span>

<span data-ttu-id="3c34a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3c34a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3c34a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c34a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c34a-105">Fractionne un tableau en plusieurs parties de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="3c34a-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="3c34a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c34a-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="3c34a-107">nElements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c34a-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c34a-108">Longueur de chaque segment.</span><span class="sxs-lookup"><span data-stu-id="3c34a-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="3c34a-109">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="3c34a-109">arr : 'T[]</span></span>

<span data-ttu-id="3c34a-110">Tableau à fractionner.</span><span class="sxs-lookup"><span data-stu-id="3c34a-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="3c34a-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="3c34a-111">Output : 'T[][]</span></span>

<span data-ttu-id="3c34a-112">Tableau contenant chaque segment du tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="3c34a-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3c34a-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3c34a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c34a-114">Peut</span><span class="sxs-lookup"><span data-stu-id="3c34a-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3c34a-115">Notes</span><span class="sxs-lookup"><span data-stu-id="3c34a-115">Remarks</span></span>

<span data-ttu-id="3c34a-116">Notez que le dernier élément de la sortie peut être plus petit que `nElements` si `Length(arr)` n’est pas divisible par `nElements` .</span><span class="sxs-lookup"><span data-stu-id="3c34a-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>