---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220193"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="0dd07-102">SquareArrayFact fonction)</span><span class="sxs-lookup"><span data-stu-id="0dd07-102">SquareArrayFact function</span></span>

<span data-ttu-id="0dd07-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0dd07-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0dd07-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0dd07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0dd07-105">Représente une condition dans laquelle un tableau à deux dimensions a une forme carrée</span><span class="sxs-lookup"><span data-stu-id="0dd07-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="0dd07-106">Description</span><span class="sxs-lookup"><span data-stu-id="0dd07-106">Description</span></span>

<span data-ttu-id="0dd07-107">Cette fonction déclare que chaque ligne d’un tableau a autant d’éléments qu’il y a de lignes (éléments) dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="0dd07-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="0dd07-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0dd07-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="0dd07-109">Tableau : 't [] []</span><span class="sxs-lookup"><span data-stu-id="0dd07-109">array : 'T[][]</span></span>

<span data-ttu-id="0dd07-110">Tableau d’éléments à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="0dd07-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="0dd07-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0dd07-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0dd07-112">Message à imprimer si le tableau n’est pas un tableau carré</span><span class="sxs-lookup"><span data-stu-id="0dd07-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="0dd07-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0dd07-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0dd07-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0dd07-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0dd07-115">Peut</span><span class="sxs-lookup"><span data-stu-id="0dd07-115">'T</span></span>

<span data-ttu-id="0dd07-116">Type de chaque élément de `array` .</span><span class="sxs-lookup"><span data-stu-id="0dd07-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dd07-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dd07-117">See Also</span></span>

- [<span data-ttu-id="0dd07-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="0dd07-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)