---
uid: Microsoft.Quantum.Arrays.Any
title: Toutes les fonctions
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221655"
---
# <a name="any-function"></a><span data-ttu-id="2c725-102">Toutes les fonctions</span><span class="sxs-lookup"><span data-stu-id="2c725-102">Any function</span></span>

<span data-ttu-id="2c725-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2c725-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2c725-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c725-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c725-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, vérifie si au moins un élément du tableau est conforme au prédicat.</span><span class="sxs-lookup"><span data-stu-id="2c725-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="2c725-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2c725-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="2c725-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c725-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c725-108">Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.</span><span class="sxs-lookup"><span data-stu-id="2c725-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="2c725-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="2c725-109">array : 'T[]</span></span>

<span data-ttu-id="2c725-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="2c725-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2c725-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c725-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c725-112">`Bool`Valeur de la fonction ou du prédicat appliquée à tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="2c725-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2c725-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2c725-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c725-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2c725-114">'T</span></span>

<span data-ttu-id="2c725-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="2c725-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c725-116">Notes</span><span class="sxs-lookup"><span data-stu-id="2c725-116">Remarks</span></span>

<span data-ttu-id="2c725-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si un élément satisfait `predicate` .</span><span class="sxs-lookup"><span data-stu-id="2c725-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>