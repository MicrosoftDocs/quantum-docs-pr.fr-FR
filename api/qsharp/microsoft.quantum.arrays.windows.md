---
uid: Microsoft.Quantum.Arrays.Windows
title: Fonction Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219887"
---
# <a name="windows-function"></a><span data-ttu-id="94da9-102">Fonction Windows</span><span class="sxs-lookup"><span data-stu-id="94da9-102">Windows function</span></span>

<span data-ttu-id="94da9-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="94da9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="94da9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94da9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94da9-105">Retourne tous les sous-tableaux consécutifs de longueur `size` .</span><span class="sxs-lookup"><span data-stu-id="94da9-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="94da9-106">Description</span><span class="sxs-lookup"><span data-stu-id="94da9-106">Description</span></span>

<span data-ttu-id="94da9-107">Cette fonction retourne tous les `n - size + 1` sous-tableaux de longueur `size` dans l’ordre, où `n` est la longueur de `arr` .</span><span class="sxs-lookup"><span data-stu-id="94da9-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="94da9-108">Les premiers sous-tableaux sont `arr[0..size - 1], arr[1..size], arr[2..size + 1]` jusqu’au dernier sous-tableau `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="94da9-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="94da9-109">Si `size <= 0` ou `size > n` , un tableau vide est retourné.</span><span class="sxs-lookup"><span data-stu-id="94da9-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="94da9-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="94da9-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="94da9-111">taille : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94da9-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94da9-112">Longueur des sous-tableaux.</span><span class="sxs-lookup"><span data-stu-id="94da9-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="94da9-113">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="94da9-113">array : 'T[]</span></span>

<span data-ttu-id="94da9-114">Tableau d’éléments.</span><span class="sxs-lookup"><span data-stu-id="94da9-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="94da9-115">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="94da9-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94da9-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="94da9-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94da9-117">Peut</span><span class="sxs-lookup"><span data-stu-id="94da9-117">'T</span></span>

<span data-ttu-id="94da9-118">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="94da9-118">The type of `array` elements.</span></span>