---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705910"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="68efe-102">LookupFunction fonction)</span><span class="sxs-lookup"><span data-stu-id="68efe-102">LookupFunction function</span></span>

<span data-ttu-id="68efe-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68efe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68efe-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68efe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68efe-105">À partir d’un tableau, retourne une fonction qui retourne des éléments de ce tableau.</span><span class="sxs-lookup"><span data-stu-id="68efe-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="68efe-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="68efe-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="68efe-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="68efe-107">array : 'T[]</span></span>

<span data-ttu-id="68efe-108">Tableau à représenter sous la forme d’une fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="68efe-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="68efe-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="68efe-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="68efe-110">Fonction de ce `f` type `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="68efe-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68efe-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="68efe-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68efe-112">Peut</span><span class="sxs-lookup"><span data-stu-id="68efe-112">'T</span></span>

<span data-ttu-id="68efe-113">Type des éléments du tableau qui est représenté comme fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="68efe-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="68efe-114">Notes</span><span class="sxs-lookup"><span data-stu-id="68efe-114">Remarks</span></span>

<span data-ttu-id="68efe-115">Cette fonction est principalement utile pour l’interopérabilité avec les fonctions et les opérations qui prennent `Int -> 'T` des fonctions comme arguments.</span><span class="sxs-lookup"><span data-stu-id="68efe-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="68efe-116">Cela est courant, par exemple, dans la bibliothèque de représentation du générateur, où les fonctions sont utilisées pour éviter d’avoir à enregistrer un tableau entier dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="68efe-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>