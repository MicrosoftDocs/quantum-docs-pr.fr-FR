---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Opération ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705014"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="c7b54-102">Opération ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="c7b54-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="c7b54-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7b54-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7b54-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7b54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7b54-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="c7b54-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="c7b54-106">Contrôl</span><span class="sxs-lookup"><span data-stu-id="c7b54-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c7b54-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c7b54-107">Input</span></span>

### <a name="listofops--t--unit-ctl"></a><span data-ttu-id="c7b54-108">listOfOps : 't [] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="c7b54-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="c7b54-109">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="c7b54-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="c7b54-110">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="c7b54-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="c7b54-111">Chaque doit avoir un functor contrôlé</span><span class="sxs-lookup"><span data-stu-id="c7b54-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="c7b54-112">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="c7b54-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="c7b54-113">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="c7b54-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="c7b54-114">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c7b54-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="c7b54-115">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="c7b54-115">register : 'T[]</span></span>

<span data-ttu-id="c7b54-116">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="c7b54-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7b54-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7b54-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c7b54-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c7b54-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7b54-119">Peut</span><span class="sxs-lookup"><span data-stu-id="c7b54-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="c7b54-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7b54-120">See Also</span></span>

- [<span data-ttu-id="c7b54-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="c7b54-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)