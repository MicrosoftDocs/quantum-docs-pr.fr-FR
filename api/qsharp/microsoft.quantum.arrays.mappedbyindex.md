---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705899"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="2e952-102">MappedByIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="2e952-102">MappedByIndex function</span></span>

<span data-ttu-id="2e952-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2e952-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2e952-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e952-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e952-105">À partir d’un tableau et d’une fonction définis pour les éléments indexés du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="2e952-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="2e952-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2e952-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="2e952-107">mappeur : ([int](xref:microsoft.quantum.lang-ref.int), 't)-> 'U</span><span class="sxs-lookup"><span data-stu-id="2e952-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="2e952-108">Fonction de `(Int, 'T)` à `'U` qui est utilisée pour mapper des éléments et leurs index.</span><span class="sxs-lookup"><span data-stu-id="2e952-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="2e952-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="2e952-109">array : 'T[]</span></span>

<span data-ttu-id="2e952-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="2e952-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="2e952-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="2e952-111">Output : 'U[]</span></span>

<span data-ttu-id="2e952-112">Tableau `'U[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="2e952-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e952-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2e952-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e952-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2e952-114">'T</span></span>

<span data-ttu-id="2e952-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="2e952-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="2e952-116">'U</span><span class="sxs-lookup"><span data-stu-id="2e952-116">'U</span></span>

<span data-ttu-id="2e952-117">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="2e952-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e952-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e952-118">See Also</span></span>

- [<span data-ttu-id="2e952-119">Microsoft. Quantum. Arrays. mapped</span><span class="sxs-lookup"><span data-stu-id="2e952-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)