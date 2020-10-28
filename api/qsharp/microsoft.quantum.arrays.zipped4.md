---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 413b415288170b4a6bffbb773e3277cdb47bdbbe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705651"
---
# <a name="zipped4-function"></a><span data-ttu-id="7fb07-102">Zipped4 fonction)</span><span class="sxs-lookup"><span data-stu-id="7fb07-102">Zipped4 function</span></span>

<span data-ttu-id="7fb07-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7fb07-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7fb07-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fb07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fb07-105">À partir de quatre tableaux, retourne un nouveau tableau de 4 tuples de telle sorte que chaque 4 tuple contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="7fb07-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="7fb07-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7fb07-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="7fb07-107">tout d’abord : 't 1 []</span><span class="sxs-lookup"><span data-stu-id="7fb07-107">first : 'T1[]</span></span>

<span data-ttu-id="7fb07-108">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="7fb07-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="7fb07-109">seconde : 't 2 []</span><span class="sxs-lookup"><span data-stu-id="7fb07-109">second : 'T2[]</span></span>

<span data-ttu-id="7fb07-110">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="7fb07-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="7fb07-111">troisième : 't 3 []</span><span class="sxs-lookup"><span data-stu-id="7fb07-111">third : 'T3[]</span></span>

<span data-ttu-id="7fb07-112">Tableau contenant des valeurs pour le troisième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="7fb07-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="7fb07-113">quatrième : t 4 []</span><span class="sxs-lookup"><span data-stu-id="7fb07-113">fourth : 'T4[]</span></span>

<span data-ttu-id="7fb07-114">Tableau contenant les valeurs du quatrième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="7fb07-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="7fb07-115">Sortie : ('t 1, 't 2, 't 3, 't 4) []</span><span class="sxs-lookup"><span data-stu-id="7fb07-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="7fb07-116">Tableau contenant 4 tuples de la forme `(first[idx], second[idx], third[idx], fourth[idx])` pour chaque `idx` .</span><span class="sxs-lookup"><span data-stu-id="7fb07-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="7fb07-117">Si les quatre tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="7fb07-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7fb07-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7fb07-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="7fb07-119">T 1</span><span class="sxs-lookup"><span data-stu-id="7fb07-119">'T1</span></span>

<span data-ttu-id="7fb07-120">Type des premiers éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="7fb07-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="7fb07-121">T 2</span><span class="sxs-lookup"><span data-stu-id="7fb07-121">'T2</span></span>

<span data-ttu-id="7fb07-122">Type du deuxième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="7fb07-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="7fb07-123">T 3</span><span class="sxs-lookup"><span data-stu-id="7fb07-123">'T3</span></span>

<span data-ttu-id="7fb07-124">Type du troisième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="7fb07-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="7fb07-125">T 4</span><span class="sxs-lookup"><span data-stu-id="7fb07-125">'T4</span></span>

<span data-ttu-id="7fb07-126">Type du quatrième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="7fb07-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fb07-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7fb07-127">See Also</span></span>

- [<span data-ttu-id="7fb07-128">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="7fb07-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="7fb07-129">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="7fb07-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)