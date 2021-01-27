---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Fonction énumérée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848122"
---
# <a name="enumerated-function"></a><span data-ttu-id="e136e-102">Fonction énumérée</span><span class="sxs-lookup"><span data-stu-id="e136e-102">Enumerated function</span></span>

<span data-ttu-id="e136e-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e136e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e136e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e136e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e136e-105">À partir d’un tableau, retourne un nouveau tableau contenant les éléments du tableau d’origine, ainsi que les index de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="e136e-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="e136e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e136e-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="e136e-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="e136e-107">array : 'TElement[]</span></span>

<span data-ttu-id="e136e-108">Tableau dont les éléments doivent être énumérés.</span><span class="sxs-lookup"><span data-stu-id="e136e-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="e136e-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), 'TElement) []</span><span class="sxs-lookup"><span data-stu-id="e136e-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="e136e-110">Nouveau tableau contenant les éléments du tableau d’origine et leurs index.</span><span class="sxs-lookup"><span data-stu-id="e136e-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e136e-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e136e-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="e136e-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="e136e-112">'TElement</span></span>

<span data-ttu-id="e136e-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="e136e-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="e136e-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="e136e-114">Example</span></span>

<span data-ttu-id="e136e-115">Les `for` boucles suivantes sont équivalentes :</span><span class="sxs-lookup"><span data-stu-id="e136e-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```