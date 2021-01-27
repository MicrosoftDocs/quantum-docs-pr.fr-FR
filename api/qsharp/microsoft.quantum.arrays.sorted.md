---
uid: Microsoft.Quantum.Arrays.Sorted
title: Fonction triée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845441"
---
# <a name="sorted-function"></a><span data-ttu-id="89180-102">Fonction triée</span><span class="sxs-lookup"><span data-stu-id="89180-102">Sorted function</span></span>

<span data-ttu-id="89180-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="89180-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="89180-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89180-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89180-105">À partir d’un tableau, retourne les éléments de ce tableau triés par une fonction de comparaison donnée.</span><span class="sxs-lookup"><span data-stu-id="89180-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="89180-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="89180-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="89180-107">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="89180-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="89180-108">Fonction qui compare deux éléments de sorte que `a` est considéré comme inférieur ou égal à `b` si `comparison(a, b)` est `true` .</span><span class="sxs-lookup"><span data-stu-id="89180-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="89180-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="89180-109">array : 'T[]</span></span>

<span data-ttu-id="89180-110">Tableau à trier.</span><span class="sxs-lookup"><span data-stu-id="89180-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="89180-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="89180-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="89180-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="89180-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89180-113">Peut</span><span class="sxs-lookup"><span data-stu-id="89180-113">'T</span></span>

<span data-ttu-id="89180-114">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="89180-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="89180-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="89180-115">Example</span></span>

<span data-ttu-id="89180-116">L’extrait de code suivant trie un tableau d’entiers pour qu’il se produise dans l’ordre croissant :</span><span class="sxs-lookup"><span data-stu-id="89180-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="89180-117">Notes</span><span class="sxs-lookup"><span data-stu-id="89180-117">Remarks</span></span>

<span data-ttu-id="89180-118">La fonction `comparison` est supposée être transitive, de sorte que si `comparison(a, b)` et `comparison(b, c)` , `comparison(a, c)` est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="89180-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="89180-119">Si cette propriété ne contient pas, la sortie de cette fonction est peut-être incorrecte.</span><span class="sxs-lookup"><span data-stu-id="89180-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="89180-120">Étant donné qu’il s’agit d’une fonction, les résultats sont complètement déterministess, même lorsque deux éléments sont considérés comme égaux, `comparison` c’est-à-dire quand `comparison(a, b)` et `comparison(b, a)` sont tous les deux `true` .</span><span class="sxs-lookup"><span data-stu-id="89180-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="89180-121">En particulier, le tri effectué par cette fonction est garanti être stable, de sorte que si deux éléments `a` et `b` se produisent dans cet ordre dans `array` et sont considérés comme étant égaux `comparison` , `a` ils apparaissent également avant `b` dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="89180-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="89180-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="89180-122">For example:</span></span>

```qsharp
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