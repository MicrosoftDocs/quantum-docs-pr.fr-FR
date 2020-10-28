---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705734"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="d3f66-102">TupleArrayAsNestedArray fonction)</span><span class="sxs-lookup"><span data-stu-id="d3f66-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="d3f66-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d3f66-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d3f66-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3f66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3f66-105">Convertit une liste de 2 tuples en tableau imbriqué.</span><span class="sxs-lookup"><span data-stu-id="d3f66-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="d3f66-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d3f66-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="d3f66-107">tupleList : (t, 't) []</span><span class="sxs-lookup"><span data-stu-id="d3f66-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="d3f66-108">Liste de 2 tuples à contourner dans un tableau imbriqué.</span><span class="sxs-lookup"><span data-stu-id="d3f66-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d3f66-109">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="d3f66-109">Output : 'T[][]</span></span>

<span data-ttu-id="d3f66-110">Tableau imbriqué dont la longueur correspond à tupleList.</span><span class="sxs-lookup"><span data-stu-id="d3f66-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="d3f66-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="d3f66-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="d3f66-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d3f66-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3f66-113">Peut</span><span class="sxs-lookup"><span data-stu-id="d3f66-113">'T</span></span>

