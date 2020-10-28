---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705811"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="1ae5c-102">RectangularArrayFact fonction)</span><span class="sxs-lookup"><span data-stu-id="1ae5c-102">RectangularArrayFact function</span></span>

<span data-ttu-id="1ae5c-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1ae5c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1ae5c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ae5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ae5c-105">Représente une condition dans laquelle un tableau à deux dimensions a une forme rectangulaire</span><span class="sxs-lookup"><span data-stu-id="1ae5c-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="1ae5c-106">Description</span><span class="sxs-lookup"><span data-stu-id="1ae5c-106">Description</span></span>

<span data-ttu-id="1ae5c-107">Cette fonction déclare que chaque ligne d’un tableau a la même longueur.</span><span class="sxs-lookup"><span data-stu-id="1ae5c-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="1ae5c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1ae5c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="1ae5c-109">Tableau : 't [] []</span><span class="sxs-lookup"><span data-stu-id="1ae5c-109">array : 'T[][]</span></span>

<span data-ttu-id="1ae5c-110">Tableau d’éléments à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="1ae5c-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="1ae5c-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1ae5c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1ae5c-112">Message à imprimer si le tableau n’est pas un tableau rectangulaire</span><span class="sxs-lookup"><span data-stu-id="1ae5c-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ae5c-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ae5c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1ae5c-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1ae5c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ae5c-115">Peut</span><span class="sxs-lookup"><span data-stu-id="1ae5c-115">'T</span></span>

<span data-ttu-id="1ae5c-116">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="1ae5c-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ae5c-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ae5c-117">See Also</span></span>

- [<span data-ttu-id="1ae5c-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="1ae5c-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)