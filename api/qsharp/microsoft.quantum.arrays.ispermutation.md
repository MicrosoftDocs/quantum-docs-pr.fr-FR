---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848093"
---
# <a name="ispermutation-function"></a><span data-ttu-id="04a87-102">IsPermutation fonction)</span><span class="sxs-lookup"><span data-stu-id="04a87-102">IsPermutation function</span></span>

<span data-ttu-id="04a87-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="04a87-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="04a87-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04a87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04a87-105">Génère la valeur true si et seulement si un tableau donné représente une permutation.</span><span class="sxs-lookup"><span data-stu-id="04a87-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="04a87-106">Description</span><span class="sxs-lookup"><span data-stu-id="04a87-106">Description</span></span>

<span data-ttu-id="04a87-107">Pour un tableau `array` de longueur donné `n` , retourne true si et seulement si chaque entier de `0` à `n - 1` apparaît exactement une fois dans `array` , ce qui `array` peut être interprété comme une permutation sur les `n` éléments.</span><span class="sxs-lookup"><span data-stu-id="04a87-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="04a87-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="04a87-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="04a87-109">permuation : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04a87-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="04a87-110">Tableau qui peut ou ne peut pas représenter une permutation.</span><span class="sxs-lookup"><span data-stu-id="04a87-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="04a87-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="04a87-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="04a87-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="04a87-112">Example</span></span>

<span data-ttu-id="04a87-113">Le code Q # suivant imprime le message « tous les diagnostics ont été effectués avec succès » :</span><span class="sxs-lookup"><span data-stu-id="04a87-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="04a87-114">Notes</span><span class="sxs-lookup"><span data-stu-id="04a87-114">Remarks</span></span>

<span data-ttu-id="04a87-115">Un tableau de longueur zéro est une permutation.</span><span class="sxs-lookup"><span data-stu-id="04a87-115">An array of length zero is trivially a permutation.</span></span>