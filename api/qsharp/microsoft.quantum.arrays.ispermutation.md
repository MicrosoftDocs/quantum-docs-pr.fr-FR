---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705934"
---
# <a name="ispermutation-function"></a><span data-ttu-id="5e9ae-102">IsPermutation fonction)</span><span class="sxs-lookup"><span data-stu-id="5e9ae-102">IsPermutation function</span></span>

<span data-ttu-id="5e9ae-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5e9ae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5e9ae-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e9ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e9ae-105">Génère la valeur true si et seulement si un tableau donné représente une permutation.</span><span class="sxs-lookup"><span data-stu-id="5e9ae-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="5e9ae-106">Description</span><span class="sxs-lookup"><span data-stu-id="5e9ae-106">Description</span></span>

<span data-ttu-id="5e9ae-107">Pour un tableau `array` de longueur donné `n` , retourne true si et seulement si chaque entier de `0` à `n - 1` apparaît exactement une fois dans `array` , ce qui `array` peut être interprété comme une permutation sur les `n` éléments.</span><span class="sxs-lookup"><span data-stu-id="5e9ae-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="5e9ae-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5e9ae-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="5e9ae-109">permuation : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5e9ae-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5e9ae-110">Tableau qui peut ou ne peut pas représenter une permutation.</span><span class="sxs-lookup"><span data-stu-id="5e9ae-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5e9ae-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e9ae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="5e9ae-112">Notes</span><span class="sxs-lookup"><span data-stu-id="5e9ae-112">Remarks</span></span>

<span data-ttu-id="5e9ae-113">Un tableau de longueur zéro est une permutation.</span><span class="sxs-lookup"><span data-stu-id="5e9ae-113">An array of length zero is trivially a permutation.</span></span>