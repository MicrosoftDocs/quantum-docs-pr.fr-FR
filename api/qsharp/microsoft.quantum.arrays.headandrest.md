---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705982"
---
# <a name="headandrest-function"></a><span data-ttu-id="b7a13-102">HeadAndRest fonction)</span><span class="sxs-lookup"><span data-stu-id="b7a13-102">HeadAndRest function</span></span>

<span data-ttu-id="b7a13-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b7a13-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b7a13-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7a13-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7a13-105">Retourne un tuple du premier et de tous les éléments restants du tableau.</span><span class="sxs-lookup"><span data-stu-id="b7a13-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="b7a13-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b7a13-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="b7a13-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="b7a13-107">array : 'A[]</span></span>

<span data-ttu-id="b7a13-108">Tableau avec au moins un élément.</span><span class="sxs-lookup"><span data-stu-id="b7a13-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="b7a13-109">Sortie : ('A, 'A [])</span><span class="sxs-lookup"><span data-stu-id="b7a13-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="b7a13-110">Tuple du premier et de tous les éléments restants du tableau.</span><span class="sxs-lookup"><span data-stu-id="b7a13-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b7a13-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b7a13-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="b7a13-112">'A</span><span class="sxs-lookup"><span data-stu-id="b7a13-112">'A</span></span>

<span data-ttu-id="b7a13-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="b7a13-113">The type of the array elements.</span></span>