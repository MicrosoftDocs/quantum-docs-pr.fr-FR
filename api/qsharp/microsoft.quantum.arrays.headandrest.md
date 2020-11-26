---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221077"
---
# <a name="headandrest-function"></a><span data-ttu-id="2b990-102">HeadAndRest fonction)</span><span class="sxs-lookup"><span data-stu-id="2b990-102">HeadAndRest function</span></span>

<span data-ttu-id="2b990-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2b990-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2b990-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b990-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b990-105">Retourne un tuple du premier et de tous les éléments restants du tableau.</span><span class="sxs-lookup"><span data-stu-id="2b990-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="2b990-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2b990-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2b990-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="2b990-107">array : 'A[]</span></span>

<span data-ttu-id="2b990-108">Tableau avec au moins un élément.</span><span class="sxs-lookup"><span data-stu-id="2b990-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="2b990-109">Sortie : ('A, 'A [])</span><span class="sxs-lookup"><span data-stu-id="2b990-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="2b990-110">Tuple du premier et de tous les éléments restants du tableau.</span><span class="sxs-lookup"><span data-stu-id="2b990-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2b990-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2b990-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2b990-112">'A</span><span class="sxs-lookup"><span data-stu-id="2b990-112">'A</span></span>

<span data-ttu-id="2b990-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="2b990-113">The type of the array elements.</span></span>