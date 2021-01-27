---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Fonction entrelacée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848110"
---
# <a name="interleaved-function"></a><span data-ttu-id="0ef8f-102">Fonction entrelacée</span><span class="sxs-lookup"><span data-stu-id="0ef8f-102">Interleaved function</span></span>

<span data-ttu-id="0ef8f-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0ef8f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0ef8f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ef8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ef8f-105">Entrelace deux tableaux de (presque) la même taille.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="0ef8f-106">Description</span><span class="sxs-lookup"><span data-stu-id="0ef8f-106">Description</span></span>

<span data-ttu-id="0ef8f-107">Cette fonction retourne l’entrelacement de deux tableaux, en commençant par le premier élément du premier tableau, puis le premier élément du deuxième tableau, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="0ef8f-108">Le premier tableau doit être de la même longueur que le second, ou peut avoir un élément supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="0ef8f-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="0ef8f-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="0ef8f-110">tout d’abord : 't []</span><span class="sxs-lookup"><span data-stu-id="0ef8f-110">first : 'T[]</span></span>

<span data-ttu-id="0ef8f-111">Premier tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="0ef8f-112">seconde : 't []</span><span class="sxs-lookup"><span data-stu-id="0ef8f-112">second : 'T[]</span></span>

<span data-ttu-id="0ef8f-113">Deuxième tableau à entrelacer.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="0ef8f-114">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="0ef8f-114">Output : 'T[]</span></span>

<span data-ttu-id="0ef8f-115">Tableau entrelacé</span><span class="sxs-lookup"><span data-stu-id="0ef8f-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0ef8f-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0ef8f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0ef8f-117">Peut</span><span class="sxs-lookup"><span data-stu-id="0ef8f-117">'T</span></span>

<span data-ttu-id="0ef8f-118">Type de chaque élément de `first` et `second` .</span><span class="sxs-lookup"><span data-stu-id="0ef8f-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="0ef8f-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ef8f-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```