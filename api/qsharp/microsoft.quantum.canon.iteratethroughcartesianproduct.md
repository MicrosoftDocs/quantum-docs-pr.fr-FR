---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Opération IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840275"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="35755-102">Opération IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="35755-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="35755-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35755-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35755-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35755-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35755-105">Applique une opération pour chaque index dans le produit cartésien de plusieurs plages.</span><span class="sxs-lookup"><span data-stu-id="35755-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="35755-106">Description</span><span class="sxs-lookup"><span data-stu-id="35755-106">Description</span></span>

<span data-ttu-id="35755-107">Applique de manière itérative une opération pour chaque élément du produit cartésien de `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="35755-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="35755-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="35755-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="35755-109">limites : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="35755-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="35755-110">Tableau spécifiant les plages sur lesquelles s’effectue l’itération, chaque plage étant spécifiée comme une longueur entière.</span><span class="sxs-lookup"><span data-stu-id="35755-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="35755-111">OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35755-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="35755-112">Opération à appeler pour chaque élément du produit cartésien donné.</span><span class="sxs-lookup"><span data-stu-id="35755-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35755-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35755-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="35755-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="35755-114">Example</span></span>

<span data-ttu-id="35755-115">Pour une opération donnée `op` , les deux extraits de code suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="35755-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="35755-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35755-116">See Also</span></span>

- [<span data-ttu-id="35755-117">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="35755-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)