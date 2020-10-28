---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705859"
---
# <a name="mostandtail-function"></a><span data-ttu-id="55049-102">MostAndTail fonction)</span><span class="sxs-lookup"><span data-stu-id="55049-102">MostAndTail function</span></span>

<span data-ttu-id="55049-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="55049-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="55049-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55049-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55049-105">Retourne un tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="55049-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="55049-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="55049-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="55049-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="55049-107">array : 'A[]</span></span>

<span data-ttu-id="55049-108">Tableau avec au moins un élément.</span><span class="sxs-lookup"><span data-stu-id="55049-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="55049-109">Sortie : ('A [], 'A')</span><span class="sxs-lookup"><span data-stu-id="55049-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="55049-110">Tuple de tous les éléments sauf un et du dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="55049-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="55049-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="55049-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="55049-112">'A</span><span class="sxs-lookup"><span data-stu-id="55049-112">'A</span></span>

<span data-ttu-id="55049-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="55049-113">The type of the array elements.</span></span>