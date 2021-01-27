---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845354"
---
# <a name="zip3-function"></a><span data-ttu-id="07327-102">Zip3 fonction)</span><span class="sxs-lookup"><span data-stu-id="07327-102">Zip3 function</span></span>

<span data-ttu-id="07327-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="07327-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="07327-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07327-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="07327-105">Zip3 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="07327-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="07327-106">Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped3>.</span><span class="sxs-lookup"><span data-stu-id="07327-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="07327-107">À partir de trois tableaux, retourne un nouveau tableau de 3 tuples de sorte que chaque 3 tuple contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="07327-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="07327-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="07327-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="07327-109">tout d’abord : 't 1 []</span><span class="sxs-lookup"><span data-stu-id="07327-109">first : 'T1[]</span></span>

<span data-ttu-id="07327-110">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="07327-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="07327-111">seconde : 't 2 []</span><span class="sxs-lookup"><span data-stu-id="07327-111">second : 'T2[]</span></span>

<span data-ttu-id="07327-112">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="07327-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="07327-113">troisième : 't 3 []</span><span class="sxs-lookup"><span data-stu-id="07327-113">third : 'T3[]</span></span>

<span data-ttu-id="07327-114">Tableau contenant des valeurs pour le troisième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="07327-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="07327-115">Sortie : ('t 1, 't 2, 't 3) []</span><span class="sxs-lookup"><span data-stu-id="07327-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="07327-116">Tableau contenant 3 tuples de la forme `(first[idx], second[idx], third[idx])` pour chaque `idx` .</span><span class="sxs-lookup"><span data-stu-id="07327-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="07327-117">Si les trois tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="07327-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07327-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="07327-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="07327-119">T 1</span><span class="sxs-lookup"><span data-stu-id="07327-119">'T1</span></span>

<span data-ttu-id="07327-120">Type des premiers éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="07327-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="07327-121">T 2</span><span class="sxs-lookup"><span data-stu-id="07327-121">'T2</span></span>

<span data-ttu-id="07327-122">Type du deuxième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="07327-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="07327-123">T 3</span><span class="sxs-lookup"><span data-stu-id="07327-123">'T3</span></span>

<span data-ttu-id="07327-124">Type du troisième élément de tableau.</span><span class="sxs-lookup"><span data-stu-id="07327-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="07327-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07327-125">See Also</span></span>

- [<span data-ttu-id="07327-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="07327-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="07327-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="07327-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)