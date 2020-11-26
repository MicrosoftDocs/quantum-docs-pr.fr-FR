---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Fonction partitionnée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220499"
---
# <a name="partitioned-function"></a><span data-ttu-id="e3b90-102">Fonction partitionnée</span><span class="sxs-lookup"><span data-stu-id="e3b90-102">Partitioned function</span></span>

<span data-ttu-id="e3b90-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e3b90-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e3b90-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3b90-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3b90-105">Fractionne un tableau en plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="e3b90-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e3b90-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e3b90-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="e3b90-107">nElements : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e3b90-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e3b90-108">Nombre d’éléments dans chaque partie d’un tableau</span><span class="sxs-lookup"><span data-stu-id="e3b90-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="e3b90-109">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="e3b90-109">arr : 'T[]</span></span>

<span data-ttu-id="e3b90-110">Tableau d’entrée à fractionner.</span><span class="sxs-lookup"><span data-stu-id="e3b90-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="e3b90-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="e3b90-111">Output : 'T[][]</span></span>

<span data-ttu-id="e3b90-112">Plusieurs tableaux dans lesquels le premier tableau est le premier `nElements[0]` `arr` et le deuxième tableau sont le suivant, `nElements[1]` `arr` etc. Le dernier tableau contiendra tous les éléments restants.</span><span class="sxs-lookup"><span data-stu-id="e3b90-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e3b90-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e3b90-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3b90-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e3b90-114">'T</span></span>

