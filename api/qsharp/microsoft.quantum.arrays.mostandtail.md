---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845601"
---
# <a name="mostandtail-function"></a><span data-ttu-id="907a6-102">MostAndTail fonction)</span><span class="sxs-lookup"><span data-stu-id="907a6-102">MostAndTail function</span></span>

<span data-ttu-id="907a6-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="907a6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="907a6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="907a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="907a6-105">Retourne un tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="907a6-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="907a6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="907a6-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="907a6-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="907a6-107">array : 'A[]</span></span>

<span data-ttu-id="907a6-108">Tableau avec au moins un élément.</span><span class="sxs-lookup"><span data-stu-id="907a6-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="907a6-109">Sortie : ('A [], 'A')</span><span class="sxs-lookup"><span data-stu-id="907a6-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="907a6-110">Tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="907a6-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="907a6-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="907a6-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="907a6-112">'A</span><span class="sxs-lookup"><span data-stu-id="907a6-112">'A</span></span>

<span data-ttu-id="907a6-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="907a6-113">The type of the array elements.</span></span>