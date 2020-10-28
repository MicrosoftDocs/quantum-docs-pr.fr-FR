---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Opération ApplyToPartitionCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 8ea437a0e25ed43eb745a7740ecd8861ced1350a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704715"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="49539-102">Opération ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="49539-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="49539-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49539-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49539-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49539-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49539-105">Applique une paire d’opérations à une partition donnée d’un registre en deux parties.</span><span class="sxs-lookup"><span data-stu-id="49539-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="49539-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="49539-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="49539-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="49539-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl--adj"></a><span data-ttu-id="49539-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) [=> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="49539-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="49539-109">Paire d’opérations à appliquer à la partition donnée.</span><span class="sxs-lookup"><span data-stu-id="49539-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="49539-110">numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49539-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49539-111">Nombre de qubits de la cible à placer dans la première partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="49539-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="49539-112">La qubits restante constitue la deuxième partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="49539-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="49539-113">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="49539-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="49539-114">Registre de qubits qui sont partitionnés et exploités par les deux opérations données.</span><span class="sxs-lookup"><span data-stu-id="49539-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49539-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49539-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="49539-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49539-116">See Also</span></span>

- [<span data-ttu-id="49539-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="49539-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)