---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705662"
---
# <a name="zip4-function"></a><span data-ttu-id="5ca49-102">Zip4 fonction)</span><span class="sxs-lookup"><span data-stu-id="5ca49-102">Zip4 function</span></span>

<span data-ttu-id="5ca49-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5ca49-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5ca49-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ca49-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="5ca49-105">Zip4 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="5ca49-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="5ca49-106">Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped4>.</span><span class="sxs-lookup"><span data-stu-id="5ca49-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="5ca49-107">À partir de quatre tableaux, retourne un nouveau tableau de 4 tuples de telle sorte que chaque 4 tuple contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="5ca49-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="5ca49-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5ca49-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="5ca49-109">tout d’abord : 't 1 []</span><span class="sxs-lookup"><span data-stu-id="5ca49-109">first : 'T1[]</span></span>

<span data-ttu-id="5ca49-110">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="5ca49-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="5ca49-111">seconde : 't 2 []</span><span class="sxs-lookup"><span data-stu-id="5ca49-111">second : 'T2[]</span></span>

<span data-ttu-id="5ca49-112">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="5ca49-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="5ca49-113">troisième : 't 3 []</span><span class="sxs-lookup"><span data-stu-id="5ca49-113">third : 'T3[]</span></span>

<span data-ttu-id="5ca49-114">Tableau contenant des valeurs pour le troisième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="5ca49-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="5ca49-115">quatrième : t 4 []</span><span class="sxs-lookup"><span data-stu-id="5ca49-115">fourth : 'T4[]</span></span>

<span data-ttu-id="5ca49-116">Tableau contenant les valeurs du quatrième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="5ca49-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="5ca49-117">Sortie : ('t 1, 't 2, 't 3, 't 4) []</span><span class="sxs-lookup"><span data-stu-id="5ca49-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="5ca49-118">Tableau contenant 4 tuples de la forme `(first[idx], second[idx], third[idx], fourth[idx])` pour chaque `idx` .</span><span class="sxs-lookup"><span data-stu-id="5ca49-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="5ca49-119">Si les quatre tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="5ca49-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5ca49-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5ca49-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="5ca49-121">T 1</span><span class="sxs-lookup"><span data-stu-id="5ca49-121">'T1</span></span>

<span data-ttu-id="5ca49-122">Type des premiers éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="5ca49-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="5ca49-123">T 2</span><span class="sxs-lookup"><span data-stu-id="5ca49-123">'T2</span></span>

<span data-ttu-id="5ca49-124">Type du deuxième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="5ca49-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="5ca49-125">T 3</span><span class="sxs-lookup"><span data-stu-id="5ca49-125">'T3</span></span>

<span data-ttu-id="5ca49-126">Type du troisième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="5ca49-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="5ca49-127">T 4</span><span class="sxs-lookup"><span data-stu-id="5ca49-127">'T4</span></span>

<span data-ttu-id="5ca49-128">Type du quatrième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="5ca49-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ca49-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ca49-129">See Also</span></span>

- [<span data-ttu-id="5ca49-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="5ca49-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="5ca49-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="5ca49-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)