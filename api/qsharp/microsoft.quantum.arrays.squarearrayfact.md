---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850964"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="ee084-102">SquareArrayFact fonction)</span><span class="sxs-lookup"><span data-stu-id="ee084-102">SquareArrayFact function</span></span>

<span data-ttu-id="ee084-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ee084-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ee084-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee084-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee084-105">Représente une condition dans laquelle un tableau à deux dimensions a une forme carrée</span><span class="sxs-lookup"><span data-stu-id="ee084-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="ee084-106">Description</span><span class="sxs-lookup"><span data-stu-id="ee084-106">Description</span></span>

<span data-ttu-id="ee084-107">Cette fonction déclare que chaque ligne d’un tableau a autant d’éléments qu’il y a de lignes (éléments) dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="ee084-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="ee084-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="ee084-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ee084-109">Tableau : 't [] []</span><span class="sxs-lookup"><span data-stu-id="ee084-109">array : 'T[][]</span></span>

<span data-ttu-id="ee084-110">Tableau d’éléments à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="ee084-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="ee084-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ee084-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ee084-112">Message à imprimer si le tableau n’est pas un tableau carré</span><span class="sxs-lookup"><span data-stu-id="ee084-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee084-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee084-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee084-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ee084-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee084-115">Peut</span><span class="sxs-lookup"><span data-stu-id="ee084-115">'T</span></span>

<span data-ttu-id="ee084-116">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="ee084-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="ee084-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="ee084-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="ee084-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee084-118">See Also</span></span>

- [<span data-ttu-id="ee084-119">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="ee084-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)