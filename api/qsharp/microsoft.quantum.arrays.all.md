---
uid: Microsoft.Quantum.Arrays.All
title: Fonction All
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842894"
---
# <a name="all-function"></a><span data-ttu-id="66b3a-102">Fonction All</span><span class="sxs-lookup"><span data-stu-id="66b3a-102">All function</span></span>

<span data-ttu-id="66b3a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="66b3a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="66b3a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66b3a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66b3a-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, et vérifie si tous les éléments du tableau répondent au prédicat.</span><span class="sxs-lookup"><span data-stu-id="66b3a-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="66b3a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="66b3a-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="66b3a-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="66b3a-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="66b3a-108">Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.</span><span class="sxs-lookup"><span data-stu-id="66b3a-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="66b3a-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="66b3a-109">array : 'T[]</span></span>

<span data-ttu-id="66b3a-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="66b3a-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="66b3a-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="66b3a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="66b3a-112">`Bool`Valeur de la fonction et du prédicat appliquée à tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="66b3a-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="66b3a-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="66b3a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66b3a-114">Peut</span><span class="sxs-lookup"><span data-stu-id="66b3a-114">'T</span></span>

<span data-ttu-id="66b3a-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="66b3a-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="66b3a-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="66b3a-116">Example</span></span>

<span data-ttu-id="66b3a-117">Le code suivant vérifie si tous les éléments du tableau sont non nuls :</span><span class="sxs-lookup"><span data-stu-id="66b3a-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="66b3a-118">Notes</span><span class="sxs-lookup"><span data-stu-id="66b3a-118">Remarks</span></span>

<span data-ttu-id="66b3a-119">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si tous les éléments répondent `predicate` .</span><span class="sxs-lookup"><span data-stu-id="66b3a-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>