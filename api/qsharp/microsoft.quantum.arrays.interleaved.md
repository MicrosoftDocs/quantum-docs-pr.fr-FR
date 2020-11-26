---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220958"
---
# <a name="interleaved-function"></a><span data-ttu-id="a1288-102">Fonction entrelacée</span><span class="sxs-lookup"><span data-stu-id="a1288-102">Interleaved function</span></span>

<span data-ttu-id="a1288-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a1288-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a1288-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1288-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1288-105">Entrelace deux tableaux de (presque) la même taille.</span><span class="sxs-lookup"><span data-stu-id="a1288-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a1288-106">Description</span><span class="sxs-lookup"><span data-stu-id="a1288-106">Description</span></span>

<span data-ttu-id="a1288-107">Cette fonction retourne l’entrelacement de deux tableaux, en commençant par le premier élément du premier tableau, puis le premier élément du deuxième tableau, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="a1288-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="a1288-108">Le premier tableau doit être de la même longueur que le second, ou peut avoir un élément supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a1288-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="a1288-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="a1288-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="a1288-110">tout d’abord : 't []</span><span class="sxs-lookup"><span data-stu-id="a1288-110">first : 'T[]</span></span>

<span data-ttu-id="a1288-111">Premier tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="a1288-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="a1288-112">seconde : 't []</span><span class="sxs-lookup"><span data-stu-id="a1288-112">second : 'T[]</span></span>

<span data-ttu-id="a1288-113">Deuxième tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="a1288-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="a1288-114">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="a1288-114">Output : 'T[]</span></span>

<span data-ttu-id="a1288-115">Tableau entrelacé</span><span class="sxs-lookup"><span data-stu-id="a1288-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a1288-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a1288-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1288-117">Peut</span><span class="sxs-lookup"><span data-stu-id="a1288-117">'T</span></span>

<span data-ttu-id="a1288-118">Type de chaque élément de `first` et `second` .</span><span class="sxs-lookup"><span data-stu-id="a1288-118">The type of each element of `first` and `second`.</span></span>