---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Opération ApplyToPartitionC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704710"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="92401-102">Opération ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="92401-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="92401-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92401-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92401-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92401-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92401-105">Applique une paire d’opérations à une partition donnée d’un registre en deux parties.</span><span class="sxs-lookup"><span data-stu-id="92401-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="92401-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="92401-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="92401-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="92401-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="92401-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92401-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="92401-109">Paire d’opérations à appliquer à la partition donnée.</span><span class="sxs-lookup"><span data-stu-id="92401-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="92401-110">numberOfQubitsToFirstArgument : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92401-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92401-111">Nombre de qubits de la cible à placer dans la première partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="92401-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="92401-112">La qubits restante constitue la deuxième partie de la partition.</span><span class="sxs-lookup"><span data-stu-id="92401-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="92401-113">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="92401-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="92401-114">Registre de qubits qui sont partitionnés et exploités par les deux opérations données.</span><span class="sxs-lookup"><span data-stu-id="92401-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92401-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92401-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="92401-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92401-116">See Also</span></span>

- [<span data-ttu-id="92401-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="92401-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)