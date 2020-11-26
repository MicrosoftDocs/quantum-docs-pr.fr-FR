---
uid: Microsoft.Quantum.Arrays.EqualA
title: Fonction Equals
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221366"
---
# <a name="equala-function"></a><span data-ttu-id="f22bf-102">Fonction Equals</span><span class="sxs-lookup"><span data-stu-id="f22bf-102">EqualA function</span></span>

<span data-ttu-id="f22bf-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f22bf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f22bf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f22bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f22bf-105">À partir de deux tableaux du même type et d’un prédicat qui est défini pour les paires d’éléments des tableaux, vérifie si les tableaux sont égaux.</span><span class="sxs-lookup"><span data-stu-id="f22bf-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="f22bf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f22bf-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="f22bf-107">égal à : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f22bf-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f22bf-108">Fonction de Tuple `('T, 'T)` à `Bool` qui est utilisée pour vérifier si deux éléments de tableaux sont égaux.</span><span class="sxs-lookup"><span data-stu-id="f22bf-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="f22bf-109">matrice1 : 't []</span><span class="sxs-lookup"><span data-stu-id="f22bf-109">array1 : 'T[]</span></span>

<span data-ttu-id="f22bf-110">Premier tableau à comparer.</span><span class="sxs-lookup"><span data-stu-id="f22bf-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="f22bf-111">matrice2 : 't []</span><span class="sxs-lookup"><span data-stu-id="f22bf-111">array2 : 'T[]</span></span>

<span data-ttu-id="f22bf-112">Deuxième tableau à comparer.</span><span class="sxs-lookup"><span data-stu-id="f22bf-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f22bf-113">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f22bf-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f22bf-114">Valeur `true` si et uniquement si `array1` et `array2` sont égaux.</span><span class="sxs-lookup"><span data-stu-id="f22bf-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="f22bf-115">Autrement dit, si les deux tableaux ont la même longueur et que tous les éléments sont égaux comme défini par `equal` .</span><span class="sxs-lookup"><span data-stu-id="f22bf-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f22bf-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f22bf-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f22bf-117">Peut</span><span class="sxs-lookup"><span data-stu-id="f22bf-117">'T</span></span>

<span data-ttu-id="f22bf-118">Type des éléments de chaque tableau.</span><span class="sxs-lookup"><span data-stu-id="f22bf-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="f22bf-119">Notes</span><span class="sxs-lookup"><span data-stu-id="f22bf-119">Remarks</span></span>

<span data-ttu-id="f22bf-120">Cette fonction est définie pour les types génériques ; autrement dit, chaque fois que nous avons deux tableaux `'T[]` et une fonction `equal: ('T, 'T) -> Bool` , cette fonction retourne une `Bool` valeur qui indique si les tableaux sont égaux.</span><span class="sxs-lookup"><span data-stu-id="f22bf-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="f22bf-121">Pour que deux tableaux soient considérés comme égaux, ils doivent avoir une longueur égale et les éléments des mêmes positions dans les tableaux doivent être égaux.</span><span class="sxs-lookup"><span data-stu-id="f22bf-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>