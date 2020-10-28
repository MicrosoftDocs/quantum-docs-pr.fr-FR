---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705979"
---
# <a name="indexof-function"></a><span data-ttu-id="7cbc2-102">IndexOf, fonction</span><span class="sxs-lookup"><span data-stu-id="7cbc2-102">IndexOf function</span></span>

<span data-ttu-id="7cbc2-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7cbc2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7cbc2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7cbc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7cbc2-105">Retourne le premier index du premier élément d’un tableau qui répond à un prédicat donné.</span><span class="sxs-lookup"><span data-stu-id="7cbc2-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="7cbc2-106">Si aucun élément de ce type n’existe, retourne-1.</span><span class="sxs-lookup"><span data-stu-id="7cbc2-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="7cbc2-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="7cbc2-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="7cbc2-108">prédicat : 't-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7cbc2-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7cbc2-109">Fonction de prédicat agissant sur les éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="7cbc2-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="7cbc2-110">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="7cbc2-110">arr : 'T[]</span></span>

<span data-ttu-id="7cbc2-111">Tableau dans lequel effectuer la recherche à l’aide du prédicat donné.</span><span class="sxs-lookup"><span data-stu-id="7cbc2-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="7cbc2-112">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7cbc2-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7cbc2-113">Soit le plus petit index `idx` , soit `predicate(arr[idx])` -1 si aucun élément de ce type n’existe.</span><span class="sxs-lookup"><span data-stu-id="7cbc2-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7cbc2-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7cbc2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cbc2-115">Peut</span><span class="sxs-lookup"><span data-stu-id="7cbc2-115">'T</span></span>

