---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220414"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="aaae3-102">RectangularArrayFact fonction)</span><span class="sxs-lookup"><span data-stu-id="aaae3-102">RectangularArrayFact function</span></span>

<span data-ttu-id="aaae3-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aaae3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aaae3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aaae3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aaae3-105">Représente une condition dans laquelle un tableau à deux dimensions a une forme rectangulaire</span><span class="sxs-lookup"><span data-stu-id="aaae3-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="aaae3-106">Description</span><span class="sxs-lookup"><span data-stu-id="aaae3-106">Description</span></span>

<span data-ttu-id="aaae3-107">Cette fonction déclare que chaque ligne d’un tableau a la même longueur.</span><span class="sxs-lookup"><span data-stu-id="aaae3-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="aaae3-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="aaae3-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="aaae3-109">Tableau : 't [] []</span><span class="sxs-lookup"><span data-stu-id="aaae3-109">array : 'T[][]</span></span>

<span data-ttu-id="aaae3-110">Tableau d’éléments à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="aaae3-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="aaae3-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="aaae3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="aaae3-112">Message à imprimer si le tableau n’est pas un tableau rectangulaire</span><span class="sxs-lookup"><span data-stu-id="aaae3-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="aaae3-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aaae3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aaae3-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="aaae3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aaae3-115">Peut</span><span class="sxs-lookup"><span data-stu-id="aaae3-115">'T</span></span>

<span data-ttu-id="aaae3-116">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="aaae3-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaae3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aaae3-117">See Also</span></span>

- [<span data-ttu-id="aaae3-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="aaae3-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)