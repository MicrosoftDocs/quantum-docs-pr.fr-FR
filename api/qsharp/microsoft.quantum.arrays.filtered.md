---
uid: Microsoft.Quantum.Arrays.Filtered
title: Fonction filtrée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221264"
---
# <a name="filtered-function"></a><span data-ttu-id="889f4-102">Fonction filtrée</span><span class="sxs-lookup"><span data-stu-id="889f4-102">Filtered function</span></span>

<span data-ttu-id="889f4-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="889f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="889f4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="889f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="889f4-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, retourne un tableau qui se compose des éléments qui satisfont au prédicat.</span><span class="sxs-lookup"><span data-stu-id="889f4-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="889f4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="889f4-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="889f4-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="889f4-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="889f4-108">Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="889f4-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="889f4-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="889f4-109">array : 'T[]</span></span>

<span data-ttu-id="889f4-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="889f4-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="889f4-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="889f4-111">Output : 'T[]</span></span>

<span data-ttu-id="889f4-112">Tableau `'T[]` d’éléments qui satisfont le prédicat.</span><span class="sxs-lookup"><span data-stu-id="889f4-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="889f4-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="889f4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="889f4-114">Peut</span><span class="sxs-lookup"><span data-stu-id="889f4-114">'T</span></span>

<span data-ttu-id="889f4-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="889f4-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="889f4-116">Notes</span><span class="sxs-lookup"><span data-stu-id="889f4-116">Remarks</span></span>

<span data-ttu-id="889f4-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et un prédicat, `'T -> Bool` nous pouvons filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="889f4-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>