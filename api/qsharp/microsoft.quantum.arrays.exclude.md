---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude (fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706051"
---
# <a name="exclude-function"></a><span data-ttu-id="2a843-102">Exclude (fonction)</span><span class="sxs-lookup"><span data-stu-id="2a843-102">Exclude function</span></span>

<span data-ttu-id="2a843-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2a843-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2a843-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a843-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a843-105">Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.</span><span class="sxs-lookup"><span data-stu-id="2a843-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2a843-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2a843-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="2a843-107">Remove : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a843-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a843-108">Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.</span><span class="sxs-lookup"><span data-stu-id="2a843-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="2a843-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="2a843-109">array : 'T[]</span></span>

<span data-ttu-id="2a843-110">Tableau dont les valeurs du tableau de sortie sont prises.</span><span class="sxs-lookup"><span data-stu-id="2a843-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="2a843-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="2a843-111">Output : 'T[]</span></span>

<span data-ttu-id="2a843-112">Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="2a843-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a843-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2a843-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a843-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2a843-114">'T</span></span>

<span data-ttu-id="2a843-115">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="2a843-115">The type of the array elements.</span></span>