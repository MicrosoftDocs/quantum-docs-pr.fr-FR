---
uid: Microsoft.Quantum.Arrays.Filtered
title: Fonction filtrée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847158"
---
# <a name="filtered-function"></a><span data-ttu-id="68806-102">Fonction filtrée</span><span class="sxs-lookup"><span data-stu-id="68806-102">Filtered function</span></span>

<span data-ttu-id="68806-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68806-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68806-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68806-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68806-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, retourne un tableau qui se compose des éléments qui satisfont au prédicat.</span><span class="sxs-lookup"><span data-stu-id="68806-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="68806-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="68806-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="68806-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68806-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68806-108">Fonction de `'T` à Boolean qui est utilisée pour filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="68806-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="68806-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="68806-109">array : 'T[]</span></span>

<span data-ttu-id="68806-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="68806-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="68806-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="68806-111">Output : 'T[]</span></span>

<span data-ttu-id="68806-112">Tableau `'T[]` d’éléments qui satisfont le prédicat.</span><span class="sxs-lookup"><span data-stu-id="68806-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68806-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="68806-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68806-114">Peut</span><span class="sxs-lookup"><span data-stu-id="68806-114">'T</span></span>

<span data-ttu-id="68806-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="68806-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="68806-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="68806-116">Example</span></span>

<span data-ttu-id="68806-117">Le code suivant illustre la fonction « filtrée ».</span><span class="sxs-lookup"><span data-stu-id="68806-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="68806-118">Un prédicat est défini à l’aide de la @"microsoft.quantum.logical.greaterthani" fonction :</span><span class="sxs-lookup"><span data-stu-id="68806-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="68806-119">Le résultat attendu à partir de cet exemple est un tableau de nombres supérieur à 5.</span><span class="sxs-lookup"><span data-stu-id="68806-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="68806-120">Notes</span><span class="sxs-lookup"><span data-stu-id="68806-120">Remarks</span></span>

<span data-ttu-id="68806-121">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et un prédicat, `'T -> Bool` nous pouvons filtrer les éléments.</span><span class="sxs-lookup"><span data-stu-id="68806-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>