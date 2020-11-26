---
uid: Microsoft.Quantum.Arrays.Unique
title: Fonction unique
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220006"
---
# <a name="unique-function"></a><span data-ttu-id="b9a67-102">Fonction unique</span><span class="sxs-lookup"><span data-stu-id="b9a67-102">Unique function</span></span>

<span data-ttu-id="b9a67-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b9a67-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b9a67-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9a67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9a67-105">Retourne un nouveau tableau qui n’a pas d’éléments adjacents égaux.</span><span class="sxs-lookup"><span data-stu-id="b9a67-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b9a67-106">Description</span><span class="sxs-lookup"><span data-stu-id="b9a67-106">Description</span></span>

<span data-ttu-id="b9a67-107">À partir d’un tableau d’éléments et d’une fonction pour tester l’égalité, cette fonction retourne un nouveau tableau dans lequel l’ordre relatif des éléments est conservé, mais tous les éléments adjacents qui sont égaux sont filtrés simplement en un seul élément.</span><span class="sxs-lookup"><span data-stu-id="b9a67-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="b9a67-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="b9a67-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="b9a67-109">égal à : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b9a67-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b9a67-110">Fonction qui compare deux éléments de sorte qu' `a` il est considéré comme égal à `b` si `equal(a, b)` est `true` .</span><span class="sxs-lookup"><span data-stu-id="b9a67-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="b9a67-111">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="b9a67-111">array : 'T[]</span></span>

<span data-ttu-id="b9a67-112">Tableau à filtrer pour les éléments uniques.</span><span class="sxs-lookup"><span data-stu-id="b9a67-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b9a67-113">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="b9a67-113">Output : 'T[]</span></span>

<span data-ttu-id="b9a67-114">Tableau sans éléments adjacents égaux.</span><span class="sxs-lookup"><span data-stu-id="b9a67-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b9a67-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b9a67-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b9a67-116">Peut</span><span class="sxs-lookup"><span data-stu-id="b9a67-116">'T</span></span>

<span data-ttu-id="b9a67-117">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="b9a67-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9a67-118">Notes</span><span class="sxs-lookup"><span data-stu-id="b9a67-118">Remarks</span></span>

<span data-ttu-id="b9a67-119">Si plusieurs éléments sont égaux, mais pas à côté, il y aura plusieurs occurrences dans le tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="b9a67-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="b9a67-120">Utilisez cette fonction conjointement avec `Sorted` pour récupérer un tableau avec des éléments uniques globaux.</span><span class="sxs-lookup"><span data-stu-id="b9a67-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>