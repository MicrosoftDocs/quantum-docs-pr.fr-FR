---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Opération ApplyToPartitionCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 572cf824647b3e7f7c0e17c797d519f41914f79d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841287"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="3e6bf-102">Opération ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="3e6bf-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="3e6bf-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e6bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e6bf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e6bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e6bf-105">Applique une paire d’opérations à une partition donnée d’un registre en deux parties.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="3e6bf-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3e6bf-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3e6bf-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="3e6bf-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="3e6bf-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3e6bf-109">Paire d’opérations à appliquer à la partition donnée.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="3e6bf-110">numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e6bf-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e6bf-111">Nombre de qubits de la cible à placer dans la première partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="3e6bf-112">La qubits restante constitue la deuxième partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3e6bf-113">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e6bf-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e6bf-114">Registre de qubits qui sont partitionnés et exploités par les deux opérations données.</span><span class="sxs-lookup"><span data-stu-id="3e6bf-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e6bf-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e6bf-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e6bf-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e6bf-116">See Also</span></span>

- [<span data-ttu-id="3e6bf-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="3e6bf-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)