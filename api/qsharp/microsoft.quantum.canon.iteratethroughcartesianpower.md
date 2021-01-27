---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Opération IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840297"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="0aa4c-102">Opération IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="0aa4c-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="0aa4c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0aa4c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0aa4c-105">Applique une opération pour chaque index dans la puissance Cartésiente d’une plage d’entiers.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0aa4c-106">Description</span><span class="sxs-lookup"><span data-stu-id="0aa4c-106">Description</span></span>

<span data-ttu-id="0aa4c-107">Applique de manière itérative une opération pour chaque élément d’une puissance Cartésiene de la plage `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="0aa4c-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="0aa4c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0aa4c-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="0aa4c-109">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0aa4c-110">Puissance Cartésiene à laquelle la plage `0..(bound - 1)` doit être levée.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="0aa4c-111">lié : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0aa4c-112">Spécification de la plage sur laquelle effectuer l’itération, en fonction de la longueur de la plage.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0aa4c-113">OP : [int](xref:microsoft.quantum.lang-ref.int)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0aa4c-114">Opération à appeler pour chaque élément de la puissance cartésien donnée.</span><span class="sxs-lookup"><span data-stu-id="0aa4c-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0aa4c-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0aa4c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="0aa4c-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="0aa4c-116">Example</span></span>

<span data-ttu-id="0aa4c-117">Pour une opération donnée `op` , les deux extraits de code suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="0aa4c-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="0aa4c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0aa4c-118">See Also</span></span>

- [<span data-ttu-id="0aa4c-119">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="0aa4c-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)