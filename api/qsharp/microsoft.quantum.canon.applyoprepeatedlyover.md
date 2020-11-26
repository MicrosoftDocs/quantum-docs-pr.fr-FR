---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: Opération ApplyOpRepeatedlyOver
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 343392d5a6af07cdc45fd8bab6656d59a6f2b350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218306"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="6e540-102">Opération ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6e540-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="6e540-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e540-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e540-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e540-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e540-105">Applique la même opération sur un registre qubit plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="6e540-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6e540-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6e540-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="6e540-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e540-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6e540-108">Opération à appliquer plusieurs fois sur le registre qubit</span><span class="sxs-lookup"><span data-stu-id="6e540-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="6e540-109">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6e540-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6e540-110">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="6e540-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6e540-111">Chaque tableau doit contenir une liste de ints décrivant le qubits à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6e540-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6e540-112">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6e540-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6e540-113">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="6e540-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e540-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e540-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6e540-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e540-115">See Also</span></span>

- [<span data-ttu-id="6e540-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="6e540-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)