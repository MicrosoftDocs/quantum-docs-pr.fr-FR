---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220941"
---
# <a name="indexrange-function"></a><span data-ttu-id="0fa81-102">IndexRange fonction)</span><span class="sxs-lookup"><span data-stu-id="0fa81-102">IndexRange function</span></span>

<span data-ttu-id="0fa81-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0fa81-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0fa81-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0fa81-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0fa81-105">À partir d’un tableau, retourne une plage sur les index de ce tableau, pouvant être utilisée dans une boucle for.</span><span class="sxs-lookup"><span data-stu-id="0fa81-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="0fa81-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0fa81-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="0fa81-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="0fa81-107">array : 'TElement[]</span></span>

<span data-ttu-id="0fa81-108">Tableau pour lequel une plage d’index doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="0fa81-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="0fa81-109">Sortie : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0fa81-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0fa81-110">Plage sur tous les index du tableau.</span><span class="sxs-lookup"><span data-stu-id="0fa81-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0fa81-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0fa81-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="0fa81-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="0fa81-112">'TElement</span></span>

<span data-ttu-id="0fa81-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="0fa81-113">The type of elements of the array.</span></span>