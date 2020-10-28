---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Opération ApplyToPartition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704726"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="69ec3-102">Opération ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="69ec3-102">ApplyToPartition operation</span></span>

<span data-ttu-id="69ec3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69ec3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69ec3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69ec3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69ec3-105">Applique une paire d’opérations à une partition donnée d’un registre en deux parties.</span><span class="sxs-lookup"><span data-stu-id="69ec3-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="69ec3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="69ec3-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="69ec3-107">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69ec3-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69ec3-108">Paire d’opérations à appliquer à la partition donnée.</span><span class="sxs-lookup"><span data-stu-id="69ec3-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="69ec3-109">numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69ec3-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69ec3-110">Nombre de qubits de la cible à placer dans la première partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="69ec3-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="69ec3-111">La qubits restante constitue la deuxième partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="69ec3-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="69ec3-112">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69ec3-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69ec3-113">Registre de qubits qui sont partitionnés et exploités par les deux opérations données.</span><span class="sxs-lookup"><span data-stu-id="69ec3-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69ec3-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69ec3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69ec3-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69ec3-115">See Also</span></span>

- [<span data-ttu-id="69ec3-116">Microsoft. Quantum. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="69ec3-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="69ec3-117">Microsoft. Quantum. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="69ec3-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="69ec3-118">Microsoft. Quantum. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="69ec3-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)