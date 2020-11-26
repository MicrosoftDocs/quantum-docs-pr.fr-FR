---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Opération ApplySeriesOfOps
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218000"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="8e0e7-102">Opération ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="8e0e7-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="8e0e7-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e0e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e0e7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e0e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e0e7-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8e0e7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8e0e7-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="8e0e7-107">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="8e0e7-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="8e0e7-108">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="8e0e7-109">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="8e0e7-110">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="8e0e7-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="8e0e7-111">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="8e0e7-112">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="8e0e7-113">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="8e0e7-113">register : 'T[]</span></span>

<span data-ttu-id="8e0e7-114">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="8e0e7-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e0e7-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e0e7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8e0e7-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="8e0e7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e0e7-117">Peut</span><span class="sxs-lookup"><span data-stu-id="8e0e7-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="8e0e7-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e0e7-118">See Also</span></span>

- [<span data-ttu-id="8e0e7-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="8e0e7-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)