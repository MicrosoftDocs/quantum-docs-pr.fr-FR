---
uid: Microsoft.Quantum.Arrays.All
title: Fonction All
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221689"
---
# <a name="all-function"></a><span data-ttu-id="44de7-102">Fonction All</span><span class="sxs-lookup"><span data-stu-id="44de7-102">All function</span></span>

<span data-ttu-id="44de7-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="44de7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="44de7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44de7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44de7-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, et vérifie si tous les éléments du tableau répondent au prédicat.</span><span class="sxs-lookup"><span data-stu-id="44de7-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="44de7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="44de7-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="44de7-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="44de7-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="44de7-108">Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.</span><span class="sxs-lookup"><span data-stu-id="44de7-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="44de7-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="44de7-109">array : 'T[]</span></span>

<span data-ttu-id="44de7-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="44de7-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="44de7-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="44de7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="44de7-112">`Bool`Valeur de la fonction et du prédicat appliquée à tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="44de7-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="44de7-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="44de7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44de7-114">Peut</span><span class="sxs-lookup"><span data-stu-id="44de7-114">'T</span></span>

<span data-ttu-id="44de7-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="44de7-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="44de7-116">Notes</span><span class="sxs-lookup"><span data-stu-id="44de7-116">Remarks</span></span>

<span data-ttu-id="44de7-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si tous les éléments répondent `predicate` .</span><span class="sxs-lookup"><span data-stu-id="44de7-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>