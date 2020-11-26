---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197582"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="22a2e-102">LexographicComparison fonction)</span><span class="sxs-lookup"><span data-stu-id="22a2e-102">LexographicComparison function</span></span>

<span data-ttu-id="22a2e-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="22a2e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="22a2e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22a2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22a2e-105">À partir d’une fonction de comparaison, retourne une nouvelle fonction que lexographically compare deux tableaux.</span><span class="sxs-lookup"><span data-stu-id="22a2e-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="22a2e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="22a2e-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="22a2e-107">elementComparison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22a2e-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22a2e-108">Fonction qui compare deux éléments `x` et `y` et retourne si `x` est inférieur ou égal à `y` .</span><span class="sxs-lookup"><span data-stu-id="22a2e-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="22a2e-109">Sortie : ('t [], 't [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22a2e-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22a2e-110">Fonction qui compare deux tableaux `xs` et `ys` et retourne si `xs` se produit avant ou égal à `ys` dans le classement lexographical.</span><span class="sxs-lookup"><span data-stu-id="22a2e-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="22a2e-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="22a2e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22a2e-112">Peut</span><span class="sxs-lookup"><span data-stu-id="22a2e-112">'T</span></span>

<span data-ttu-id="22a2e-113">Type des éléments des tableaux comparés.</span><span class="sxs-lookup"><span data-stu-id="22a2e-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="22a2e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="22a2e-114">Remarks</span></span>

<span data-ttu-id="22a2e-115">La comparaison lexographic entre deux tableaux `xs` et `ys` est définie par la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="22a2e-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="22a2e-116">Nous disons que deux éléments `x` et `y` sont équivalents si `elementComparison(x, y)` et `elementComparison(y, x)` sont tous les deux vrais.</span><span class="sxs-lookup"><span data-stu-id="22a2e-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="22a2e-117">Les deux tableaux sont comparés élément par élément jusqu’à la première paire d’éléments qui ne sont pas équivalents.</span><span class="sxs-lookup"><span data-stu-id="22a2e-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="22a2e-118">Le tableau contenant l’élément qui se produit en premier en fonction de `elementComparison` est dit se produire en premier dans le classement lexographical.</span><span class="sxs-lookup"><span data-stu-id="22a2e-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="22a2e-119">Si aucun élément inéquivalent n’est trouvé et que l’un des tableaux est plus long que l’autre, le tableau le plus petit est dit en premier.</span><span class="sxs-lookup"><span data-stu-id="22a2e-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="22a2e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22a2e-120">See Also</span></span>

- [<span data-ttu-id="22a2e-121">Microsoft. Quantum. Arrays. tri</span><span class="sxs-lookup"><span data-stu-id="22a2e-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)