---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Opération ApplySeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841494"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="7abf4-102">Opération ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="7abf4-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="7abf4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7abf4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7abf4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7abf4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7abf4-105">Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="7abf4-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7abf4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7abf4-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="7abf4-107">listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="7abf4-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="7abf4-108">Liste des opérations, chacune utilisant un tableau t, à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7abf4-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="7abf4-109">Elles sont appliquées séquentiellement, le plus bas en premier.</span><span class="sxs-lookup"><span data-stu-id="7abf4-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="7abf4-110">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="7abf4-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="7abf4-111">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="7abf4-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="7abf4-112">Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.</span><span class="sxs-lookup"><span data-stu-id="7abf4-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="7abf4-113">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="7abf4-113">register : 'T[]</span></span>

<span data-ttu-id="7abf4-114">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="7abf4-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7abf4-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7abf4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7abf4-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7abf4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7abf4-117">Peut</span><span class="sxs-lookup"><span data-stu-id="7abf4-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="7abf4-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="7abf4-118">Example</span></span>

<span data-ttu-id="7abf4-119">L’exemple suivant applique exp ([PauliX, PauliY], 0,5) à qubits 0, 1//Then X à qubit 2 Let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; Let index = [[0, 1], [2]]; ApplySeriesOfOps (OPS, index, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="7abf4-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="7abf4-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7abf4-120">See Also</span></span>

- [<span data-ttu-id="7abf4-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="7abf4-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)