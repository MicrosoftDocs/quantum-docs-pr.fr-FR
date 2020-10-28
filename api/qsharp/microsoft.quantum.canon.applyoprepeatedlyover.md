---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: Opération ApplyOpRepeatedlyOver
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705131"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="499b3-102">Opération ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="499b3-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="499b3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="499b3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="499b3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="499b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="499b3-105">Applique la même opération sur un registre qubit plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="499b3-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="499b3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="499b3-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="499b3-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="499b3-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="499b3-108">Opération à appliquer plusieurs fois sur le registre qubit</span><span class="sxs-lookup"><span data-stu-id="499b3-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="499b3-109">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="499b3-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="499b3-110">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="499b3-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="499b3-111">Chaque tableau doit contenir une liste de ints décrivant le qubits à utiliser.</span><span class="sxs-lookup"><span data-stu-id="499b3-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="499b3-112">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="499b3-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="499b3-113">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="499b3-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="499b3-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="499b3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="499b3-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="499b3-115">See Also</span></span>

- [<span data-ttu-id="499b3-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="499b3-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)