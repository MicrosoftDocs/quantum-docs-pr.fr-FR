---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845667"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="c0390-102">MappedByIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="c0390-102">MappedByIndex function</span></span>

<span data-ttu-id="c0390-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c0390-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c0390-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0390-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0390-105">À partir d’un tableau et d’une fonction définis pour les éléments indexés du tableau, retourne un nouveau tableau qui se compose des images du tableau d’origine sous la fonction.</span><span class="sxs-lookup"><span data-stu-id="c0390-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c0390-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c0390-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="c0390-107">mappeur : ([int](xref:microsoft.quantum.lang-ref.int), 't)-> 'U</span><span class="sxs-lookup"><span data-stu-id="c0390-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="c0390-108">Fonction de `(Int, 'T)` à `'U` qui est utilisée pour mapper des éléments et leurs index.</span><span class="sxs-lookup"><span data-stu-id="c0390-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="c0390-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="c0390-109">array : 'T[]</span></span>

<span data-ttu-id="c0390-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="c0390-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c0390-111">Sortie : 'U []</span><span class="sxs-lookup"><span data-stu-id="c0390-111">Output : 'U[]</span></span>

<span data-ttu-id="c0390-112">Tableau `'U[]` d’éléments mappés par la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="c0390-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c0390-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c0390-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0390-114">Peut</span><span class="sxs-lookup"><span data-stu-id="c0390-114">'T</span></span>

<span data-ttu-id="c0390-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="c0390-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c0390-116">'U</span><span class="sxs-lookup"><span data-stu-id="c0390-116">'U</span></span>

<span data-ttu-id="c0390-117">Type de résultat de la `mapper` fonction.</span><span class="sxs-lookup"><span data-stu-id="c0390-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="c0390-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="c0390-118">Example</span></span>

<span data-ttu-id="c0390-119">Les deux lignes suivantes sont équivalentes :</span><span class="sxs-lookup"><span data-stu-id="c0390-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="c0390-120">and</span><span class="sxs-lookup"><span data-stu-id="c0390-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="c0390-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c0390-121">See Also</span></span>

- [<span data-ttu-id="c0390-122">Microsoft. Quantum. Arrays. mapped</span><span class="sxs-lookup"><span data-stu-id="c0390-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)