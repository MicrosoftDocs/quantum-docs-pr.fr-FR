---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Fonction partitionnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845539"
---
# <a name="partitioned-function"></a><span data-ttu-id="6800d-102">Fonction partitionnée</span><span class="sxs-lookup"><span data-stu-id="6800d-102">Partitioned function</span></span>

<span data-ttu-id="6800d-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6800d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6800d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6800d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6800d-105">Fractionne un tableau en plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="6800d-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="6800d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6800d-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="6800d-107">nElements : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6800d-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6800d-108">Nombre d’éléments dans chaque partie d’un tableau</span><span class="sxs-lookup"><span data-stu-id="6800d-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="6800d-109">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="6800d-109">arr : 'T[]</span></span>

<span data-ttu-id="6800d-110">Tableau d’entrée à fractionner.</span><span class="sxs-lookup"><span data-stu-id="6800d-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="6800d-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="6800d-111">Output : 'T[][]</span></span>

<span data-ttu-id="6800d-112">Plusieurs tableaux dans lesquels le premier tableau est le premier `nElements[0]` `arr` et le deuxième tableau sont le suivant, `nElements[1]` `arr` etc. Le dernier tableau contiendra tous les éléments restants.</span><span class="sxs-lookup"><span data-stu-id="6800d-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6800d-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6800d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6800d-114">Peut</span><span class="sxs-lookup"><span data-stu-id="6800d-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="6800d-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="6800d-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```