---
uid: Microsoft.Quantum.Arrays.Sorted
title: Fonction triée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220227"
---
# <a name="sorted-function"></a><span data-ttu-id="ab16e-102">Fonction triée</span><span class="sxs-lookup"><span data-stu-id="ab16e-102">Sorted function</span></span>

<span data-ttu-id="ab16e-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ab16e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ab16e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab16e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab16e-105">À partir d’un tableau, retourne les éléments de ce tableau triés par une fonction de comparaison donnée.</span><span class="sxs-lookup"><span data-stu-id="ab16e-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ab16e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ab16e-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="ab16e-107">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab16e-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab16e-108">Fonction qui compare deux éléments de sorte que `a` est considéré comme inférieur ou égal à `b` si `comparison(a, b)` est `true` .</span><span class="sxs-lookup"><span data-stu-id="ab16e-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="ab16e-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="ab16e-109">array : 'T[]</span></span>

<span data-ttu-id="ab16e-110">Tableau à trier.</span><span class="sxs-lookup"><span data-stu-id="ab16e-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="ab16e-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="ab16e-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab16e-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ab16e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab16e-113">Peut</span><span class="sxs-lookup"><span data-stu-id="ab16e-113">'T</span></span>

<span data-ttu-id="ab16e-114">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="ab16e-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab16e-115">Notes</span><span class="sxs-lookup"><span data-stu-id="ab16e-115">Remarks</span></span>

<span data-ttu-id="ab16e-116">La fonction `comparison` est supposée être transitive, de sorte que si `comparison(a, b)` et `comparison(b, c)` , `comparison(a, c)` est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="ab16e-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="ab16e-117">Si cette propriété ne contient pas, la sortie de cette fonction est peut-être incorrecte.</span><span class="sxs-lookup"><span data-stu-id="ab16e-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="ab16e-118">Étant donné qu’il s’agit d’une fonction, les résultats sont complètement déterministess, même lorsque deux éléments sont considérés comme égaux, `comparison` c’est-à-dire quand `comparison(a, b)` et `comparison(b, a)` sont tous les deux `true` .</span><span class="sxs-lookup"><span data-stu-id="ab16e-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="ab16e-119">En particulier, le tri effectué par cette fonction est garanti être stable, de sorte que si deux éléments `a` et `b` se produisent dans cet ordre dans `array` et sont considérés comme étant égaux `comparison` , `a` ils apparaissent également avant `b` dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="ab16e-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="ab16e-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ab16e-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```