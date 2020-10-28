---
uid: Microsoft.Quantum.Arrays.Subarray
title: SubArray, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705758"
---
# <a name="subarray-function"></a><span data-ttu-id="c5e38-102">SubArray, fonction</span><span class="sxs-lookup"><span data-stu-id="c5e38-102">Subarray function</span></span>

<span data-ttu-id="c5e38-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5e38-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5e38-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5e38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5e38-105">Prend un tableau et une liste d’emplacements et produit un nouveau tableau formé à partir des éléments du tableau d’origine qui correspondent aux emplacements donnés.</span><span class="sxs-lookup"><span data-stu-id="c5e38-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c5e38-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c5e38-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="c5e38-107">index : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5e38-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5e38-108">Liste d’entiers utilisée pour définir le sous-tableau.</span><span class="sxs-lookup"><span data-stu-id="c5e38-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="c5e38-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="c5e38-109">array : 'T[]</span></span>

<span data-ttu-id="c5e38-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="c5e38-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="c5e38-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="c5e38-111">Output : 'T[]</span></span>

<span data-ttu-id="c5e38-112">Tableau `out` d’éléments dont les index correspondent au sous-tableau, de telle sorte que `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="c5e38-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5e38-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c5e38-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5e38-114">Peut</span><span class="sxs-lookup"><span data-stu-id="c5e38-114">'T</span></span>

<span data-ttu-id="c5e38-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="c5e38-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5e38-116">Notes</span><span class="sxs-lookup"><span data-stu-id="c5e38-116">Remarks</span></span>

<span data-ttu-id="c5e38-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une liste d’emplacements `Int[]` définissant le sous-tableau.</span><span class="sxs-lookup"><span data-stu-id="c5e38-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="c5e38-118">La construction du sous-tableau est basée sur la génération d’une nouvelle copie complète du tableau donné au lieu de conserver les références.</span><span class="sxs-lookup"><span data-stu-id="c5e38-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="c5e38-119">Si `Length(indices) < Length(array)` la condition est, cette fonction retourne un sous-ensemble de `array` .</span><span class="sxs-lookup"><span data-stu-id="c5e38-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="c5e38-120">En revanche, si contient des `indices` éléments répétés, les éléments correspondants de `array` sont de la même façon répétés.</span><span class="sxs-lookup"><span data-stu-id="c5e38-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="c5e38-121">Si `indices` et `array` sont de la même longueur, cette fonction fournit des permutations de `array` .</span><span class="sxs-lookup"><span data-stu-id="c5e38-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>