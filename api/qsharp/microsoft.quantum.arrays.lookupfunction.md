---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845697"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="553e2-102">LookupFunction fonction)</span><span class="sxs-lookup"><span data-stu-id="553e2-102">LookupFunction function</span></span>

<span data-ttu-id="553e2-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="553e2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="553e2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="553e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="553e2-105">À partir d’un tableau, retourne une fonction qui retourne des éléments de ce tableau.</span><span class="sxs-lookup"><span data-stu-id="553e2-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="553e2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="553e2-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="553e2-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="553e2-107">array : 'T[]</span></span>

<span data-ttu-id="553e2-108">Tableau à représenter sous la forme d’une fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="553e2-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="553e2-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="553e2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="553e2-110">Fonction de ce `f` type `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="553e2-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="553e2-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="553e2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="553e2-112">Peut</span><span class="sxs-lookup"><span data-stu-id="553e2-112">'T</span></span>

<span data-ttu-id="553e2-113">Type des éléments du tableau qui est représenté comme fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="553e2-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="553e2-114">Notes</span><span class="sxs-lookup"><span data-stu-id="553e2-114">Remarks</span></span>

<span data-ttu-id="553e2-115">Cette fonction est principalement utile pour l’interopérabilité avec les fonctions et les opérations qui prennent `Int -> 'T` des fonctions comme arguments.</span><span class="sxs-lookup"><span data-stu-id="553e2-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="553e2-116">Cela est courant, par exemple, dans la bibliothèque de représentation du générateur, où les fonctions sont utilisées pour éviter d’avoir à enregistrer un tableau entier dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="553e2-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>