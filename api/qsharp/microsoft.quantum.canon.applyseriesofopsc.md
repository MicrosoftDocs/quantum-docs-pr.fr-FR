---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Opération ApplySeriesOfOpsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844643"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="65853-102">Opération ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="65853-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="65853-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65853-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65853-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65853-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65853-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="65853-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="65853-106">Contrôl</span><span class="sxs-lookup"><span data-stu-id="65853-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="65853-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="65853-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="65853-108">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL []</span><span class="sxs-lookup"><span data-stu-id="65853-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="65853-109">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="65853-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="65853-110">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="65853-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="65853-111">Chaque doit avoir un functor contrôlé</span><span class="sxs-lookup"><span data-stu-id="65853-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="65853-112">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="65853-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="65853-113">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="65853-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="65853-114">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="65853-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="65853-115">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="65853-115">register : 'T[]</span></span>

<span data-ttu-id="65853-116">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="65853-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65853-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65853-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65853-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="65853-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65853-119">Peut</span><span class="sxs-lookup"><span data-stu-id="65853-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="65853-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="65853-120">Example</span></span>

<span data-ttu-id="65853-121">L’exemple suivant applique exp ([PauliX, PauliY], 0,5) à qubits 0, 1//Then X à qubit 2 Let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitC (X, _)]; Let index = [[0, 1], [2]]; ApplySeriesOfOpsC (OPS, index, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="65853-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="65853-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65853-122">See Also</span></span>

- [<span data-ttu-id="65853-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="65853-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)