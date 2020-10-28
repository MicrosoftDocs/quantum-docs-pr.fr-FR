---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705958"
---
# <a name="interleaved-function"></a><span data-ttu-id="276eb-102">Fonction entrelacée</span><span class="sxs-lookup"><span data-stu-id="276eb-102">Interleaved function</span></span>

<span data-ttu-id="276eb-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="276eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="276eb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="276eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="276eb-105">Entrelace deux tableaux de (presque) la même taille.</span><span class="sxs-lookup"><span data-stu-id="276eb-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="276eb-106">Description</span><span class="sxs-lookup"><span data-stu-id="276eb-106">Description</span></span>

<span data-ttu-id="276eb-107">Cette fonction retourne l’entrelacement de deux tableaux, en commençant par le premier élément du premier tableau, puis le premier élément du deuxième tableau, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="276eb-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="276eb-108">Le premier tableau doit être de la même longueur que le second, ou peut avoir un élément supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="276eb-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="276eb-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="276eb-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="276eb-110">tout d’abord : 't []</span><span class="sxs-lookup"><span data-stu-id="276eb-110">first : 'T[]</span></span>

<span data-ttu-id="276eb-111">Premier tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="276eb-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="276eb-112">seconde : 't []</span><span class="sxs-lookup"><span data-stu-id="276eb-112">second : 'T[]</span></span>

<span data-ttu-id="276eb-113">Deuxième tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="276eb-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="276eb-114">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="276eb-114">Output : 'T[]</span></span>

<span data-ttu-id="276eb-115">Tableau entrelacé</span><span class="sxs-lookup"><span data-stu-id="276eb-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="276eb-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="276eb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="276eb-117">Peut</span><span class="sxs-lookup"><span data-stu-id="276eb-117">'T</span></span>

<span data-ttu-id="276eb-118">Type de chaque élément de `first` et `second` .</span><span class="sxs-lookup"><span data-stu-id="276eb-118">The type of each element of `first` and `second`.</span></span>