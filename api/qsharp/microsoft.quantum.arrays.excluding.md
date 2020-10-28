---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exclusion de la fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706046"
---
# <a name="excluding-function"></a><span data-ttu-id="d0a1a-102">Exclusion de la fonction</span><span class="sxs-lookup"><span data-stu-id="d0a1a-102">Excluding function</span></span>

<span data-ttu-id="d0a1a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0a1a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0a1a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0a1a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0a1a-105">Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.</span><span class="sxs-lookup"><span data-stu-id="d0a1a-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d0a1a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d0a1a-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="d0a1a-107">Remove : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d0a1a-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d0a1a-108">Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.</span><span class="sxs-lookup"><span data-stu-id="d0a1a-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="d0a1a-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="d0a1a-109">array : 'T[]</span></span>

<span data-ttu-id="d0a1a-110">Tableau dont les valeurs du tableau de sortie sont prises.</span><span class="sxs-lookup"><span data-stu-id="d0a1a-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0a1a-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="d0a1a-111">Output : 'T[]</span></span>

<span data-ttu-id="d0a1a-112">Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="d0a1a-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0a1a-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d0a1a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0a1a-114">Peut</span><span class="sxs-lookup"><span data-stu-id="d0a1a-114">'T</span></span>

<span data-ttu-id="d0a1a-115">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="d0a1a-115">The type of the array elements.</span></span>