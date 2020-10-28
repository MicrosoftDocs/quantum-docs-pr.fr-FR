---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Fonction énumérée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706067"
---
# <a name="enumerated-function"></a><span data-ttu-id="b00c8-102">Fonction énumérée</span><span class="sxs-lookup"><span data-stu-id="b00c8-102">Enumerated function</span></span>

<span data-ttu-id="b00c8-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b00c8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b00c8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b00c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b00c8-105">À partir d’un tableau, retourne un nouveau tableau contenant les éléments du tableau d’origine, ainsi que les index de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="b00c8-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="b00c8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b00c8-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="b00c8-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="b00c8-107">array : 'TElement[]</span></span>

<span data-ttu-id="b00c8-108">Tableau dont les éléments doivent être énumérés.</span><span class="sxs-lookup"><span data-stu-id="b00c8-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="b00c8-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), 'TElement) []</span><span class="sxs-lookup"><span data-stu-id="b00c8-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="b00c8-110">Nouveau tableau contenant les éléments du tableau d’origine et leurs index.</span><span class="sxs-lookup"><span data-stu-id="b00c8-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b00c8-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b00c8-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="b00c8-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="b00c8-112">'TElement</span></span>

<span data-ttu-id="b00c8-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="b00c8-113">The type of elements of the array.</span></span>