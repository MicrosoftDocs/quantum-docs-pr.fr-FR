---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705678"
---
# <a name="zip3-function"></a><span data-ttu-id="b3205-102">Zip3 fonction)</span><span class="sxs-lookup"><span data-stu-id="b3205-102">Zip3 function</span></span>

<span data-ttu-id="b3205-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b3205-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b3205-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3205-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="b3205-105">Zip3 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="b3205-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="b3205-106">Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped3>.</span><span class="sxs-lookup"><span data-stu-id="b3205-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="b3205-107">À partir de trois tableaux, retourne un nouveau tableau de 3 tuples de sorte que chaque 3 tuple contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="b3205-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b3205-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="b3205-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b3205-109">tout d’abord : 't 1 []</span><span class="sxs-lookup"><span data-stu-id="b3205-109">first : 'T1[]</span></span>

<span data-ttu-id="b3205-110">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="b3205-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b3205-111">seconde : 't 2 []</span><span class="sxs-lookup"><span data-stu-id="b3205-111">second : 'T2[]</span></span>

<span data-ttu-id="b3205-112">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="b3205-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b3205-113">troisième : 't 3 []</span><span class="sxs-lookup"><span data-stu-id="b3205-113">third : 'T3[]</span></span>

<span data-ttu-id="b3205-114">Tableau contenant des valeurs pour le troisième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="b3205-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b3205-115">Sortie : ('t 1, 't 2, 't 3) []</span><span class="sxs-lookup"><span data-stu-id="b3205-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b3205-116">Tableau contenant 3 tuples de la forme `(first[idx], second[idx], third[idx])` pour chaque `idx` .</span><span class="sxs-lookup"><span data-stu-id="b3205-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b3205-117">Si les trois tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="b3205-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b3205-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b3205-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b3205-119">T 1</span><span class="sxs-lookup"><span data-stu-id="b3205-119">'T1</span></span>

<span data-ttu-id="b3205-120">Type des premiers éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="b3205-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b3205-121">T 2</span><span class="sxs-lookup"><span data-stu-id="b3205-121">'T2</span></span>

<span data-ttu-id="b3205-122">Type du deuxième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="b3205-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b3205-123">T 3</span><span class="sxs-lookup"><span data-stu-id="b3205-123">'T3</span></span>

<span data-ttu-id="b3205-124">Type du troisième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="b3205-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3205-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3205-125">See Also</span></span>

- [<span data-ttu-id="b3205-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="b3205-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="b3205-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="b3205-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)