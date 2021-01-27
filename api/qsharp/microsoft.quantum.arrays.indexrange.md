---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845777"
---
# <a name="indexrange-function"></a><span data-ttu-id="89d7f-102">IndexRange fonction)</span><span class="sxs-lookup"><span data-stu-id="89d7f-102">IndexRange function</span></span>

<span data-ttu-id="89d7f-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="89d7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="89d7f-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="89d7f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="89d7f-105">À partir d’un tableau, retourne une plage sur les index de ce tableau, pouvant être utilisée dans une boucle for.</span><span class="sxs-lookup"><span data-stu-id="89d7f-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="89d7f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="89d7f-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="89d7f-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="89d7f-107">array : 'TElement[]</span></span>

<span data-ttu-id="89d7f-108">Tableau pour lequel une plage d’index doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="89d7f-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="89d7f-109">Sortie : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="89d7f-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="89d7f-110">Plage sur tous les index du tableau.</span><span class="sxs-lookup"><span data-stu-id="89d7f-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="89d7f-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="89d7f-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="89d7f-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="89d7f-112">'TElement</span></span>

<span data-ttu-id="89d7f-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="89d7f-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="89d7f-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="89d7f-114">Example</span></span>

<span data-ttu-id="89d7f-115">Les `for` boucles suivantes sont équivalentes :</span><span class="sxs-lookup"><span data-stu-id="89d7f-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```