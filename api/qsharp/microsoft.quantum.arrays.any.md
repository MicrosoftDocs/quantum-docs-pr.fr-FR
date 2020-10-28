---
uid: Microsoft.Quantum.Arrays.Any
title: Toutes les fonctions
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706179"
---
# <a name="any-function"></a><span data-ttu-id="acaeb-102">Toutes les fonctions</span><span class="sxs-lookup"><span data-stu-id="acaeb-102">Any function</span></span>

<span data-ttu-id="acaeb-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="acaeb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="acaeb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="acaeb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="acaeb-105">À partir d’un tableau et d’un prédicat définis pour les éléments du tableau, vérifie si au moins un élément du tableau est conforme au prédicat.</span><span class="sxs-lookup"><span data-stu-id="acaeb-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="acaeb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="acaeb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="acaeb-107">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="acaeb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="acaeb-108">Fonction de `'T` à `Bool` qui est utilisée pour vérifier les éléments.</span><span class="sxs-lookup"><span data-stu-id="acaeb-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="acaeb-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="acaeb-109">array : 'T[]</span></span>

<span data-ttu-id="acaeb-110">Tableau d’éléments sur `'T` .</span><span class="sxs-lookup"><span data-stu-id="acaeb-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="acaeb-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="acaeb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="acaeb-112">`Bool`Valeur de la fonction ou du prédicat appliquée à tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="acaeb-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="acaeb-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="acaeb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="acaeb-114">Peut</span><span class="sxs-lookup"><span data-stu-id="acaeb-114">'T</span></span>

<span data-ttu-id="acaeb-115">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="acaeb-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="acaeb-116">Notes</span><span class="sxs-lookup"><span data-stu-id="acaeb-116">Remarks</span></span>

<span data-ttu-id="acaeb-117">La fonction est définie pour les types génériques, c’est-à-dire, chaque fois que nous avons un tableau `'T[]` et une fonction, `predicate: 'T -> Bool` nous pouvons produire une `Bool` valeur qui indique si un élément satisfait `predicate` .</span><span class="sxs-lookup"><span data-stu-id="acaeb-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>