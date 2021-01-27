---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude (fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848675"
---
# <a name="exclude-function"></a><span data-ttu-id="18dbe-102">Exclude (fonction)</span><span class="sxs-lookup"><span data-stu-id="18dbe-102">Exclude function</span></span>

<span data-ttu-id="18dbe-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="18dbe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="18dbe-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18dbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18dbe-105">Retourne un tableau contenant les éléments d’un autre tableau, en excluant les éléments d’une liste donnée d’index.</span><span class="sxs-lookup"><span data-stu-id="18dbe-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="18dbe-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="18dbe-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="18dbe-107">Remove : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="18dbe-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="18dbe-108">Tableau d’index indiquant les éléments qui doivent être exclus de la sortie.</span><span class="sxs-lookup"><span data-stu-id="18dbe-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="18dbe-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="18dbe-109">array : 'T[]</span></span>

<span data-ttu-id="18dbe-110">Tableau dont les valeurs du tableau de sortie sont prises.</span><span class="sxs-lookup"><span data-stu-id="18dbe-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="18dbe-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="18dbe-111">Output : 'T[]</span></span>

<span data-ttu-id="18dbe-112">Tableau `output` de type qui `output[0]` est le premier élément de `array` dont l’index n’apparaît pas dans, de sorte `remove` qu’il `output[1]` s’agit du deuxième élément de ce type, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="18dbe-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="18dbe-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="18dbe-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18dbe-114">Peut</span><span class="sxs-lookup"><span data-stu-id="18dbe-114">'T</span></span>

<span data-ttu-id="18dbe-115">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="18dbe-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="18dbe-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="18dbe-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```