---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Opération ApplyOpRepeatedlyOverA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 2e8ef7e943cfd2c0634f16566a018f386aad659f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705126"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="70653-102">Opération ApplyOpRepeatedlyOverA</span><span class="sxs-lookup"><span data-stu-id="70653-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="70653-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70653-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70653-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70653-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70653-105">Applique la même opération sur un registre qubit plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="70653-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="70653-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="70653-106">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="70653-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70653-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="70653-108">Opération à appliquer plusieurs fois sur le registre qubit</span><span class="sxs-lookup"><span data-stu-id="70653-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="70653-109">cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="70653-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="70653-110">Tableaux imbriqués décrivant les cibles du op.</span><span class="sxs-lookup"><span data-stu-id="70653-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="70653-111">Chaque tableau doit contenir une liste de ints décrivant le qubits à utiliser.</span><span class="sxs-lookup"><span data-stu-id="70653-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="70653-112">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70653-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70653-113">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="70653-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70653-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70653-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="70653-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70653-115">See Also</span></span>

- [<span data-ttu-id="70653-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="70653-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)