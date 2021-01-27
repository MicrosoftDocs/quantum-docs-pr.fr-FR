---
uid: Microsoft.Quantum.Arrays.Excluding
title: Exclusion de la fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848652"
---
# <a name="excluding-function"></a><span data-ttu-id="75cd8-102">Exclusion de la fonction</span><span class="sxs-lookup"><span data-stu-id="75cd8-102">Excluding function</span></span>

<span data-ttu-id="75cd8-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="75cd8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="75cd8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75cd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75cd8-105">Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.</span><span class="sxs-lookup"><span data-stu-id="75cd8-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="75cd8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="75cd8-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="75cd8-107">Remove : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="75cd8-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="75cd8-108">Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.</span><span class="sxs-lookup"><span data-stu-id="75cd8-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="75cd8-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="75cd8-109">array : 'T[]</span></span>

<span data-ttu-id="75cd8-110">Tableau dont les valeurs du tableau de sortie sont prises.</span><span class="sxs-lookup"><span data-stu-id="75cd8-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="75cd8-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="75cd8-111">Output : 'T[]</span></span>

<span data-ttu-id="75cd8-112">Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="75cd8-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="75cd8-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="75cd8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75cd8-114">Peut</span><span class="sxs-lookup"><span data-stu-id="75cd8-114">'T</span></span>

<span data-ttu-id="75cd8-115">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="75cd8-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="75cd8-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="75cd8-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```