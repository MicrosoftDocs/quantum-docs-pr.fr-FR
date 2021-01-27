---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845388"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="71bea-102">TupleArrayAsNestedArray fonction)</span><span class="sxs-lookup"><span data-stu-id="71bea-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="71bea-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="71bea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="71bea-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71bea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71bea-105">Convertit une liste de 2 tuples en tableau imbriqué.</span><span class="sxs-lookup"><span data-stu-id="71bea-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="71bea-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="71bea-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="71bea-107">tupleList : (t, 't) []</span><span class="sxs-lookup"><span data-stu-id="71bea-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="71bea-108">Liste de 2 tuples à contourner dans un tableau imbriqué.</span><span class="sxs-lookup"><span data-stu-id="71bea-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="71bea-109">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="71bea-109">Output : 'T[][]</span></span>

<span data-ttu-id="71bea-110">Tableau imbriqué dont la longueur correspond à tupleList.</span><span class="sxs-lookup"><span data-stu-id="71bea-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="71bea-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="71bea-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="71bea-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="71bea-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71bea-113">Peut</span><span class="sxs-lookup"><span data-stu-id="71bea-113">'T</span></span>

