---
uid: Microsoft.Quantum.Arrays.Count
title: Count (fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221553"
---
# <a name="count-function"></a><span data-ttu-id="f8245-102">Count (fonction)</span><span class="sxs-lookup"><span data-stu-id="f8245-102">Count function</span></span>

<span data-ttu-id="f8245-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f8245-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f8245-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8245-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8245-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, retourne le nombre d’éléments d’un tableau qui se compose des éléments qui satisfont au prédicat.</span><span class="sxs-lookup"><span data-stu-id="f8245-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="f8245-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f8245-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f8245-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8245-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8245-108">Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="f8245-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f8245-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="f8245-109">array : 'T[]</span></span>

<span data-ttu-id="f8245-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="f8245-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="f8245-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8245-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8245-112">Nombre d’éléments dans `array` qui satisfont le prédicat.</span><span class="sxs-lookup"><span data-stu-id="f8245-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f8245-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f8245-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8245-114">Peut</span><span class="sxs-lookup"><span data-stu-id="f8245-114">'T</span></span>

<span data-ttu-id="f8245-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="f8245-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8245-116">Notes</span><span class="sxs-lookup"><span data-stu-id="f8245-116">Remarks</span></span>

<span data-ttu-id="f8245-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et un prédicat, `'T -> Bool` nous pouvons filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="f8245-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>