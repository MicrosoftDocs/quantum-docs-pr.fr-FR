---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Opération ApplySeriesOfOpsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217966"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="71bcd-102">Opération ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="71bcd-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="71bcd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71bcd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71bcd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71bcd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71bcd-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="71bcd-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="71bcd-106">(Voisin)</span><span class="sxs-lookup"><span data-stu-id="71bcd-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="71bcd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="71bcd-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="71bcd-108">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est ADJ []</span><span class="sxs-lookup"><span data-stu-id="71bcd-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="71bcd-109">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="71bcd-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="71bcd-110">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="71bcd-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="71bcd-111">Chaque doit avoir un functor joint</span><span class="sxs-lookup"><span data-stu-id="71bcd-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="71bcd-112">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="71bcd-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="71bcd-113">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="71bcd-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="71bcd-114">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="71bcd-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="71bcd-115">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="71bcd-115">register : 'T[]</span></span>

<span data-ttu-id="71bcd-116">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="71bcd-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71bcd-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71bcd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71bcd-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="71bcd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71bcd-119">Peut</span><span class="sxs-lookup"><span data-stu-id="71bcd-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="71bcd-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71bcd-120">See Also</span></span>

- [<span data-ttu-id="71bcd-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="71bcd-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)