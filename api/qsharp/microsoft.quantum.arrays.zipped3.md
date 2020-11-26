---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219683"
---
# <a name="zipped3-function"></a><span data-ttu-id="81fa6-102">Zipped3 fonction)</span><span class="sxs-lookup"><span data-stu-id="81fa6-102">Zipped3 function</span></span>

<span data-ttu-id="81fa6-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="81fa6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="81fa6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81fa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81fa6-105">À partir de trois tableaux, retourne un nouveau tableau de 3 tuples de sorte que chaque 3 tuple contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="81fa6-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="81fa6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="81fa6-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="81fa6-107">tout d’abord : 't 1 []</span><span class="sxs-lookup"><span data-stu-id="81fa6-107">first : 'T1[]</span></span>

<span data-ttu-id="81fa6-108">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="81fa6-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="81fa6-109">seconde : 't 2 []</span><span class="sxs-lookup"><span data-stu-id="81fa6-109">second : 'T2[]</span></span>

<span data-ttu-id="81fa6-110">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="81fa6-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="81fa6-111">troisième : 't 3 []</span><span class="sxs-lookup"><span data-stu-id="81fa6-111">third : 'T3[]</span></span>

<span data-ttu-id="81fa6-112">Tableau contenant des valeurs pour le troisième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="81fa6-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="81fa6-113">Sortie : ('t 1, 't 2, 't 3) []</span><span class="sxs-lookup"><span data-stu-id="81fa6-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="81fa6-114">Tableau contenant 3 tuples de la forme `(first[idx], second[idx], third[idx])` pour chaque `idx` .</span><span class="sxs-lookup"><span data-stu-id="81fa6-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="81fa6-115">Si les trois tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="81fa6-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="81fa6-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="81fa6-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="81fa6-117">T 1</span><span class="sxs-lookup"><span data-stu-id="81fa6-117">'T1</span></span>

<span data-ttu-id="81fa6-118">Type des premiers éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="81fa6-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="81fa6-119">T 2</span><span class="sxs-lookup"><span data-stu-id="81fa6-119">'T2</span></span>

<span data-ttu-id="81fa6-120">Type du deuxième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="81fa6-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="81fa6-121">T 3</span><span class="sxs-lookup"><span data-stu-id="81fa6-121">'T3</span></span>

<span data-ttu-id="81fa6-122">Type du troisième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="81fa6-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="81fa6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81fa6-123">See Also</span></span>

- [<span data-ttu-id="81fa6-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="81fa6-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="81fa6-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="81fa6-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)