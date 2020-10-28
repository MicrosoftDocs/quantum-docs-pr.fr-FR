---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Opération ApplyDeltaParity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708642"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="97bcd-102">Opération ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="97bcd-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="97bcd-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="97bcd-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="97bcd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97bcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97bcd-105">Calcule la différence de parité entre un PQRS précédent... termes et PQRS suivant... terme.</span><span class="sxs-lookup"><span data-stu-id="97bcd-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="97bcd-106">Cette différence est calculée sur un qubit auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="97bcd-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="97bcd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="97bcd-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="97bcd-108">prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="97bcd-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="97bcd-109">Liste des index sur les PQRS précédents... vue.</span><span class="sxs-lookup"><span data-stu-id="97bcd-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="97bcd-110">nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="97bcd-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="97bcd-111">Liste des index à la PQRS suivante... vue.</span><span class="sxs-lookup"><span data-stu-id="97bcd-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="97bcd-112">aux : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97bcd-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97bcd-113">Qubit auxiliaire sur lequel sont stockés les résultats du calcul de la parité.</span><span class="sxs-lookup"><span data-stu-id="97bcd-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="97bcd-114">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="97bcd-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="97bcd-115">Qubit traité par tous les PQRS... vue.</span><span class="sxs-lookup"><span data-stu-id="97bcd-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97bcd-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97bcd-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="97bcd-117">Notes</span><span class="sxs-lookup"><span data-stu-id="97bcd-117">Remarks</span></span>

<span data-ttu-id="97bcd-118">Cela suppose que les index de P < Q < R < S <... pour prevPQ et nextPQ.</span><span class="sxs-lookup"><span data-stu-id="97bcd-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>