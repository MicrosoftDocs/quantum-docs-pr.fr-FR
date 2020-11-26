---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude (fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221349"
---
# <a name="exclude-function"></a><span data-ttu-id="15291-102">Exclude (fonction)</span><span class="sxs-lookup"><span data-stu-id="15291-102">Exclude function</span></span>

<span data-ttu-id="15291-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="15291-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="15291-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15291-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15291-105">Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.</span><span class="sxs-lookup"><span data-stu-id="15291-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="15291-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="15291-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="15291-107">Remove : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="15291-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="15291-108">Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.</span><span class="sxs-lookup"><span data-stu-id="15291-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="15291-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="15291-109">array : 'T[]</span></span>

<span data-ttu-id="15291-110">Tableau dont les valeurs du tableau de sortie sont prises.</span><span class="sxs-lookup"><span data-stu-id="15291-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="15291-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="15291-111">Output : 'T[]</span></span>

<span data-ttu-id="15291-112">Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="15291-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="15291-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="15291-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15291-114">Peut</span><span class="sxs-lookup"><span data-stu-id="15291-114">'T</span></span>

<span data-ttu-id="15291-115">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="15291-115">The type of the array elements.</span></span>