---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705963"
---
# <a name="indexrange-function"></a><span data-ttu-id="c4102-102">IndexRange fonction)</span><span class="sxs-lookup"><span data-stu-id="c4102-102">IndexRange function</span></span>

<span data-ttu-id="c4102-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4102-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4102-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4102-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4102-105">À partir d’un tableau, retourne une plage sur les index de ce tableau, pouvant être utilisée dans une boucle for.</span><span class="sxs-lookup"><span data-stu-id="c4102-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="c4102-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c4102-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="c4102-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="c4102-107">array : 'TElement[]</span></span>

<span data-ttu-id="c4102-108">Tableau pour lequel une plage d’index doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="c4102-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="c4102-109">Sortie : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c4102-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c4102-110">Plage sur tous les index du tableau.</span><span class="sxs-lookup"><span data-stu-id="c4102-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4102-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c4102-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="c4102-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="c4102-112">'TElement</span></span>

<span data-ttu-id="c4102-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="c4102-113">The type of elements of the array.</span></span>