---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Opération ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705118"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="3c88d-102">Opération ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="3c88d-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="3c88d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c88d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c88d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c88d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c88d-105">Applique la même opération sur un registre qubit plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="3c88d-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3c88d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c88d-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="3c88d-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c88d-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3c88d-108">Opération à appliquer plusieurs fois sur le registre qubit</span><span class="sxs-lookup"><span data-stu-id="3c88d-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="3c88d-109">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="3c88d-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="3c88d-110">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="3c88d-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="3c88d-111">Chaque tableau doit contenir une liste de ints décrivant le qubits à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3c88d-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3c88d-112">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c88d-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c88d-113">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="3c88d-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c88d-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c88d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3c88d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c88d-115">See Also</span></span>

- [<span data-ttu-id="3c88d-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="3c88d-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)