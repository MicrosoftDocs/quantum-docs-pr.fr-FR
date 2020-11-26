---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220567"
---
# <a name="mostandtail-function"></a><span data-ttu-id="fc8a9-102">MostAndTail fonction)</span><span class="sxs-lookup"><span data-stu-id="fc8a9-102">MostAndTail function</span></span>

<span data-ttu-id="fc8a9-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc8a9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc8a9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc8a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc8a9-105">Retourne un tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="fc8a9-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="fc8a9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fc8a9-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fc8a9-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="fc8a9-107">array : 'A[]</span></span>

<span data-ttu-id="fc8a9-108">Tableau avec au moins un élément.</span><span class="sxs-lookup"><span data-stu-id="fc8a9-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="fc8a9-109">Sortie : ('A [], 'A')</span><span class="sxs-lookup"><span data-stu-id="fc8a9-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="fc8a9-110">Tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="fc8a9-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc8a9-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fc8a9-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fc8a9-112">'A</span><span class="sxs-lookup"><span data-stu-id="fc8a9-112">'A</span></span>

<span data-ttu-id="fc8a9-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="fc8a9-113">The type of the array elements.</span></span>