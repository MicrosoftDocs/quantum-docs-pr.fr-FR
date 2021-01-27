---
uid: Microsoft.Quantum.Arrays.Subarray
title: SubArray, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845432"
---
# <a name="subarray-function"></a><span data-ttu-id="b4807-102">SubArray, fonction</span><span class="sxs-lookup"><span data-stu-id="b4807-102">Subarray function</span></span>

<span data-ttu-id="b4807-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b4807-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b4807-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4807-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4807-105">Prend un tableau et une liste d’emplacements et produit un nouveau tableau formé à partir des éléments du tableau d’origine qui correspondent aux emplacements donnés.</span><span class="sxs-lookup"><span data-stu-id="b4807-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b4807-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b4807-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="b4807-107">index : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b4807-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b4807-108">Liste d’entiers utilisée pour définir le sous-tableau.</span><span class="sxs-lookup"><span data-stu-id="b4807-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="b4807-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="b4807-109">array : 'T[]</span></span>

<span data-ttu-id="b4807-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="b4807-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="b4807-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="b4807-111">Output : 'T[]</span></span>

<span data-ttu-id="b4807-112">Tableau `out` d’éléments dont les index correspondent au sous-tableau, de telle sorte que `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="b4807-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b4807-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b4807-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b4807-114">Peut</span><span class="sxs-lookup"><span data-stu-id="b4807-114">'T</span></span>

<span data-ttu-id="b4807-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="b4807-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4807-116">Notes</span><span class="sxs-lookup"><span data-stu-id="b4807-116">Remarks</span></span>

<span data-ttu-id="b4807-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une liste d’emplacements `Int[]` définissant le sous-tableau.</span><span class="sxs-lookup"><span data-stu-id="b4807-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="b4807-118">La construction du sous-tableau est basée sur la génération d’une nouvelle copie complète du tableau donné au lieu de conserver les références.</span><span class="sxs-lookup"><span data-stu-id="b4807-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="b4807-119">Si `Length(indices) < Length(array)` la condition est, cette fonction retourne un sous-ensemble de `array` .</span><span class="sxs-lookup"><span data-stu-id="b4807-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="b4807-120">En revanche, si contient des `indices` éléments répétés, les éléments correspondants de `array` sont de la même façon répétés.</span><span class="sxs-lookup"><span data-stu-id="b4807-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="b4807-121">Si `indices` et `array` sont de la même longueur, cette fonction fournit des permutations de `array` .</span><span class="sxs-lookup"><span data-stu-id="b4807-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>