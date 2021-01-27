---
uid: Microsoft.Quantum.Arrays.Where
title: Where, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842222"
---
# <a name="where-function"></a><span data-ttu-id="e71af-102">Where, fonction</span><span class="sxs-lookup"><span data-stu-id="e71af-102">Where function</span></span>

<span data-ttu-id="e71af-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e71af-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e71af-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e71af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e71af-105">À partir d’un prédicat et d’un tableau, retourne les index de ce tableau où le prédicat a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="e71af-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="e71af-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e71af-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e71af-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e71af-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e71af-108">Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="e71af-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="e71af-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="e71af-109">array : 'T[]</span></span>

<span data-ttu-id="e71af-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="e71af-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e71af-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e71af-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e71af-112">Tableau d’index où `predicate` a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="e71af-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e71af-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e71af-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e71af-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e71af-114">'T</span></span>

<span data-ttu-id="e71af-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="e71af-115">The type of `array` elements.</span></span>