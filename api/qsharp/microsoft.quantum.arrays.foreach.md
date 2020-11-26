---
uid: Microsoft.Quantum.Arrays.ForEach
title: Opération ForEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221145"
---
# <a name="foreach-operation"></a><span data-ttu-id="ddba4-102">Opération ForEach</span><span class="sxs-lookup"><span data-stu-id="ddba4-102">ForEach operation</span></span>

<span data-ttu-id="ddba4-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ddba4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ddba4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddba4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddba4-105">À partir d’un tableau et d’une opération définie pour les éléments du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous l’opération.</span><span class="sxs-lookup"><span data-stu-id="ddba4-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="ddba4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ddba4-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="ddba4-107">action : 't => 'U</span><span class="sxs-lookup"><span data-stu-id="ddba4-107">action : 'T => 'U</span></span> 

<span data-ttu-id="ddba4-108">Opération de `'T` à `'U` qui est appliquée à chaque élément.</span><span class="sxs-lookup"><span data-stu-id="ddba4-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="ddba4-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="ddba4-109">array : 'T[]</span></span>

<span data-ttu-id="ddba4-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="ddba4-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="ddba4-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="ddba4-111">Output : 'U[]</span></span>

<span data-ttu-id="ddba4-112">Tableau `'U[]` d’éléments mappés par l' `action` opération.</span><span class="sxs-lookup"><span data-stu-id="ddba4-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ddba4-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ddba4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ddba4-114">Peut</span><span class="sxs-lookup"><span data-stu-id="ddba4-114">'T</span></span>

<span data-ttu-id="ddba4-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="ddba4-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="ddba4-116">'U</span><span class="sxs-lookup"><span data-stu-id="ddba4-116">'U</span></span>

<span data-ttu-id="ddba4-117">Type de résultat de l' `action` opération.</span><span class="sxs-lookup"><span data-stu-id="ddba4-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="ddba4-118">Notes</span><span class="sxs-lookup"><span data-stu-id="ddba4-118">Remarks</span></span>

<span data-ttu-id="ddba4-119">L’opération est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une opération, `action : 'T -> 'U` nous pouvons mapper les éléments du tableau et produire un nouveau tableau de type `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="ddba4-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>