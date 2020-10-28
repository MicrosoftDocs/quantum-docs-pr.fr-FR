---
uid: Microsoft.Quantum.Arrays.Mapped
title: Fonction mappée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705915"
---
# <a name="mapped-function"></a><span data-ttu-id="0bff0-102">Fonction mappée</span><span class="sxs-lookup"><span data-stu-id="0bff0-102">Mapped function</span></span>

<span data-ttu-id="0bff0-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0bff0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0bff0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bff0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bff0-105">À partir d’un tableau et d’une fonction définis pour les éléments du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="0bff0-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="0bff0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0bff0-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="0bff0-107">mappeur : t-> 'U</span><span class="sxs-lookup"><span data-stu-id="0bff0-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="0bff0-108">Fonction de `'T` à `'U` qui est utilisée pour mapper des éléments.</span><span class="sxs-lookup"><span data-stu-id="0bff0-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="0bff0-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="0bff0-109">array : 'T[]</span></span>

<span data-ttu-id="0bff0-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="0bff0-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="0bff0-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="0bff0-111">Output : 'U[]</span></span>

<span data-ttu-id="0bff0-112">Tableau `'U[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="0bff0-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0bff0-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0bff0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bff0-114">Peut</span><span class="sxs-lookup"><span data-stu-id="0bff0-114">'T</span></span>

<span data-ttu-id="0bff0-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="0bff0-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="0bff0-116">'U</span><span class="sxs-lookup"><span data-stu-id="0bff0-116">'U</span></span>

<span data-ttu-id="0bff0-117">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="0bff0-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="0bff0-118">Notes</span><span class="sxs-lookup"><span data-stu-id="0bff0-118">Remarks</span></span>

<span data-ttu-id="0bff0-119">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `mapper: 'T -> 'U` nous pouvons mapper les éléments du tableau et produire un nouveau tableau de type `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="0bff0-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>