---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209925"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="9a319-102">MappedByIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="9a319-102">MappedByIndex function</span></span>

<span data-ttu-id="9a319-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9a319-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9a319-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a319-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a319-105">À partir d’un tableau et d’une fonction définis pour les éléments indexés du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="9a319-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="9a319-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9a319-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="9a319-107">mappeur : ([int](xref:microsoft.quantum.lang-ref.int), 't)-> 'U</span><span class="sxs-lookup"><span data-stu-id="9a319-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="9a319-108">Fonction de `(Int, 'T)` à `'U` qui est utilisée pour mapper des éléments et leurs index.</span><span class="sxs-lookup"><span data-stu-id="9a319-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="9a319-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="9a319-109">array : 'T[]</span></span>

<span data-ttu-id="9a319-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="9a319-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="9a319-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="9a319-111">Output : 'U[]</span></span>

<span data-ttu-id="9a319-112">Tableau `'U[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="9a319-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a319-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9a319-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a319-114">Peut</span><span class="sxs-lookup"><span data-stu-id="9a319-114">'T</span></span>

<span data-ttu-id="9a319-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="9a319-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="9a319-116">'U</span><span class="sxs-lookup"><span data-stu-id="9a319-116">'U</span></span>

<span data-ttu-id="9a319-117">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="9a319-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a319-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a319-118">See Also</span></span>

- [<span data-ttu-id="9a319-119">Microsoft. Quantum. Arrays. mapped</span><span class="sxs-lookup"><span data-stu-id="9a319-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)