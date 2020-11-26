---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Opération ApplyDeltaParity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225752"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="928dd-102">Opération ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="928dd-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="928dd-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="928dd-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="928dd-104">Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="928dd-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="928dd-105">Calcule la différence de parité entre un PQRS précédent... termes et PQRS suivant... terme.</span><span class="sxs-lookup"><span data-stu-id="928dd-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="928dd-106">Cette différence est calculée sur un qubit auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="928dd-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="928dd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="928dd-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="928dd-108">prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="928dd-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="928dd-109">Liste des index sur les PQRS précédents... vue.</span><span class="sxs-lookup"><span data-stu-id="928dd-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="928dd-110">nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="928dd-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="928dd-111">Liste des index à la PQRS suivante... vue.</span><span class="sxs-lookup"><span data-stu-id="928dd-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="928dd-112">aux : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="928dd-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="928dd-113">Qubit auxiliaire sur lequel sont stockés les résultats du calcul de la parité.</span><span class="sxs-lookup"><span data-stu-id="928dd-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="928dd-114">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="928dd-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="928dd-115">Qubit traité par tous les PQRS... vue.</span><span class="sxs-lookup"><span data-stu-id="928dd-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="928dd-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="928dd-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="928dd-117">Notes</span><span class="sxs-lookup"><span data-stu-id="928dd-117">Remarks</span></span>

<span data-ttu-id="928dd-118">Cela suppose que les index de P < Q < R < S <... pour prevPQ et nextPQ.</span><span class="sxs-lookup"><span data-stu-id="928dd-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>