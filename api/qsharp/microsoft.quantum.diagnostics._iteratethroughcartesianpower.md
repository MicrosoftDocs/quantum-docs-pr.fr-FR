---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: opération de _iterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702826"
---
# <a name="_iteratethroughcartesianpower-operation"></a><span data-ttu-id="c686d-102">opération de _iterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="c686d-102">_iterateThroughCartesianPower operation</span></span>

<span data-ttu-id="c686d-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c686d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c686d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c686d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c686d-105">Itère une variable à l’aide d’un produit cartésien [0, limites [0]-1] × [0, limites [1]-1] × [0, limites [longueur (limites)-1]-1] et appelle op (arr) pour chaque élément du produit cartésien</span><span class="sxs-lookup"><span data-stu-id="c686d-105">Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product</span></span>

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="c686d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c686d-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="c686d-107">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c686d-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="value--int"></a><span data-ttu-id="c686d-108">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c686d-108">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--int--unit"></a><span data-ttu-id="c686d-109">OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c686d-109">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="c686d-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c686d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

