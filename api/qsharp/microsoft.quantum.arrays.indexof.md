---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848527"
---
# <a name="indexof-function"></a><span data-ttu-id="b444f-102">IndexOf, fonction</span><span class="sxs-lookup"><span data-stu-id="b444f-102">IndexOf function</span></span>

<span data-ttu-id="b444f-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b444f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b444f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b444f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b444f-105">Retourne le premier index du premier élément d’un tableau qui répond à un prédicat donné.</span><span class="sxs-lookup"><span data-stu-id="b444f-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="b444f-106">Si aucun élément de ce type n’existe, retourne-1.</span><span class="sxs-lookup"><span data-stu-id="b444f-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="b444f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="b444f-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="b444f-108">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b444f-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b444f-109">Fonction de prédicat agissant sur les éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="b444f-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="b444f-110">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="b444f-110">arr : 'T[]</span></span>

<span data-ttu-id="b444f-111">Tableau dans lequel effectuer la recherche à l’aide du prédicat donné.</span><span class="sxs-lookup"><span data-stu-id="b444f-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="b444f-112">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b444f-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b444f-113">Soit le plus petit index `idx` , soit `predicate(arr[idx])` -1 si aucun élément de ce type n’existe.</span><span class="sxs-lookup"><span data-stu-id="b444f-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b444f-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b444f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b444f-115">Peut</span><span class="sxs-lookup"><span data-stu-id="b444f-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="b444f-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="b444f-116">Example</span></span>

<span data-ttu-id="b444f-117">Supposons que `IsEven : Int -> Bool` est une fonction qui retourne `true` si et seulement si son entrée est paire.</span><span class="sxs-lookup"><span data-stu-id="b444f-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="b444f-118">Ensuite, il peut être utilisé avec `IndexOf` pour rechercher le premier élément pair d’un tableau :</span><span class="sxs-lookup"><span data-stu-id="b444f-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```