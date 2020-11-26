---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Opération ApplySeriesOfOpsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217932"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="cfec7-102">Opération ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="cfec7-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="cfec7-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cfec7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cfec7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfec7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfec7-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="cfec7-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="cfec7-106">Contrôl</span><span class="sxs-lookup"><span data-stu-id="cfec7-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="cfec7-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="cfec7-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="cfec7-108">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL []</span><span class="sxs-lookup"><span data-stu-id="cfec7-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="cfec7-109">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="cfec7-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="cfec7-110">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="cfec7-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="cfec7-111">Chaque doit avoir un functor contrôlé</span><span class="sxs-lookup"><span data-stu-id="cfec7-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="cfec7-112">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="cfec7-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="cfec7-113">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="cfec7-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="cfec7-114">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfec7-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="cfec7-115">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="cfec7-115">register : 'T[]</span></span>

<span data-ttu-id="cfec7-116">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="cfec7-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfec7-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfec7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cfec7-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="cfec7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfec7-119">Peut</span><span class="sxs-lookup"><span data-stu-id="cfec7-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="cfec7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfec7-120">See Also</span></span>

- [<span data-ttu-id="cfec7-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="cfec7-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)