---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Opération ApplySeriesOfOpsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217881"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="2672c-102">Opération ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="2672c-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="2672c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2672c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2672c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2672c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2672c-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="2672c-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="2672c-106">(Voisint + contrôlé)</span><span class="sxs-lookup"><span data-stu-id="2672c-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2672c-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="2672c-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="2672c-108">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="2672c-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="2672c-109">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="2672c-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="2672c-110">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="2672c-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="2672c-111">Chaque doit avoir un functor et un functor contrôlés.</span><span class="sxs-lookup"><span data-stu-id="2672c-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="2672c-112">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="2672c-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="2672c-113">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="2672c-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="2672c-114">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2672c-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="2672c-115">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="2672c-115">register : 'T[]</span></span>

<span data-ttu-id="2672c-116">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="2672c-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2672c-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2672c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2672c-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2672c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2672c-119">Peut</span><span class="sxs-lookup"><span data-stu-id="2672c-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="2672c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2672c-120">See Also</span></span>

- [<span data-ttu-id="2672c-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="2672c-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)