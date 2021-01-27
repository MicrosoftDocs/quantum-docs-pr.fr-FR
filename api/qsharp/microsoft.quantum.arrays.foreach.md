---
uid: Microsoft.Quantum.Arrays.ForEach
title: Opération ForEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848585"
---
# <a name="foreach-operation"></a><span data-ttu-id="e281d-102">Opération ForEach</span><span class="sxs-lookup"><span data-stu-id="e281d-102">ForEach operation</span></span>

<span data-ttu-id="e281d-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e281d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e281d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e281d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e281d-105">À partir d’un tableau et d’une opération définie pour les éléments du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous l’opération.</span><span class="sxs-lookup"><span data-stu-id="e281d-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="e281d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e281d-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="e281d-107">action : 't => 'U</span><span class="sxs-lookup"><span data-stu-id="e281d-107">action : 'T => 'U</span></span> 

<span data-ttu-id="e281d-108">Opération de `'T` à `'U` qui est appliquée à chaque élément.</span><span class="sxs-lookup"><span data-stu-id="e281d-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="e281d-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="e281d-109">array : 'T[]</span></span>

<span data-ttu-id="e281d-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="e281d-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="e281d-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="e281d-111">Output : 'U[]</span></span>

<span data-ttu-id="e281d-112">Tableau `'U[]` d’éléments mappés par l' `action` opération.</span><span class="sxs-lookup"><span data-stu-id="e281d-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e281d-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e281d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e281d-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e281d-114">'T</span></span>

<span data-ttu-id="e281d-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="e281d-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="e281d-116">'U</span><span class="sxs-lookup"><span data-stu-id="e281d-116">'U</span></span>

<span data-ttu-id="e281d-117">Type de résultat de l' `action` opération.</span><span class="sxs-lookup"><span data-stu-id="e281d-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="e281d-118">Notes</span><span class="sxs-lookup"><span data-stu-id="e281d-118">Remarks</span></span>

<span data-ttu-id="e281d-119">L’opération est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une opération, `action : 'T -> 'U` nous pouvons mapper les éléments du tableau et produire un nouveau tableau de type `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="e281d-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>