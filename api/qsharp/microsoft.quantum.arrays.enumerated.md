---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Fonction énumérée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221417"
---
# <a name="enumerated-function"></a><span data-ttu-id="399a8-102">Fonction énumérée</span><span class="sxs-lookup"><span data-stu-id="399a8-102">Enumerated function</span></span>

<span data-ttu-id="399a8-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="399a8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="399a8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="399a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="399a8-105">À partir d’un tableau, retourne un nouveau tableau contenant les éléments du tableau d’origine, ainsi que les index de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="399a8-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="399a8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="399a8-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="399a8-107">Tableau : 'TElement []</span><span class="sxs-lookup"><span data-stu-id="399a8-107">array : 'TElement[]</span></span>

<span data-ttu-id="399a8-108">Tableau dont les éléments doivent être énumérés.</span><span class="sxs-lookup"><span data-stu-id="399a8-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="399a8-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), 'TElement) []</span><span class="sxs-lookup"><span data-stu-id="399a8-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="399a8-110">Nouveau tableau contenant les éléments du tableau d’origine et leurs index.</span><span class="sxs-lookup"><span data-stu-id="399a8-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="399a8-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="399a8-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="399a8-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="399a8-112">'TElement</span></span>

<span data-ttu-id="399a8-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="399a8-113">The type of elements of the array.</span></span>