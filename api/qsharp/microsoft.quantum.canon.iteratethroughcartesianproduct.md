---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Opération IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704094"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="287a6-102">Opération IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="287a6-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="287a6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="287a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="287a6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="287a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="287a6-105">Applique une opération pour chaque index dans le produit cartésien de plusieurs plages.</span><span class="sxs-lookup"><span data-stu-id="287a6-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="287a6-106">Description</span><span class="sxs-lookup"><span data-stu-id="287a6-106">Description</span></span>

<span data-ttu-id="287a6-107">Applique de manière itérative une opération pour chaque élément du produit cartésien de `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="287a6-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="287a6-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="287a6-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="287a6-109">limites : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="287a6-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="287a6-110">Tableau spécifiant les plages sur lesquelles s’effectue l’itération, chaque plage étant spécifiée comme une longueur entière.</span><span class="sxs-lookup"><span data-stu-id="287a6-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="287a6-111">OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="287a6-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="287a6-112">Opération à appeler pour chaque élément du produit cartésien donné.</span><span class="sxs-lookup"><span data-stu-id="287a6-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="287a6-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="287a6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="287a6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="287a6-114">See Also</span></span>

- [<span data-ttu-id="287a6-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="287a6-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)