---
uid: Microsoft.Quantum.Arrays.Where
title: Where, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219921"
---
# <a name="where-function"></a><span data-ttu-id="883fe-102">Where, fonction</span><span class="sxs-lookup"><span data-stu-id="883fe-102">Where function</span></span>

<span data-ttu-id="883fe-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="883fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="883fe-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="883fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="883fe-105">À partir d’un prédicat et d’un tableau, retourne les index de ce tableau où le prédicat a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="883fe-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="883fe-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="883fe-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="883fe-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="883fe-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="883fe-108">Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="883fe-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="883fe-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="883fe-109">array : 'T[]</span></span>

<span data-ttu-id="883fe-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="883fe-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="883fe-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="883fe-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="883fe-112">Tableau d’index où `predicate` a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="883fe-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="883fe-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="883fe-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="883fe-114">Peut</span><span class="sxs-lookup"><span data-stu-id="883fe-114">'T</span></span>

<span data-ttu-id="883fe-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="883fe-115">The type of `array` elements.</span></span>