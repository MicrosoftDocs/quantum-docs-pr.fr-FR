---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Opération ApplyCNOTChainWithTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219105"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="80e49-102">Opération ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="80e49-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="80e49-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80e49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80e49-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80e49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80e49-105">Calcule la parité d’un tableau de qubits dans un qubit cible.</span><span class="sxs-lookup"><span data-stu-id="80e49-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="80e49-106">Description</span><span class="sxs-lookup"><span data-stu-id="80e49-106">Description</span></span>

<span data-ttu-id="80e49-107">Si le tableau est initialement dans l’État $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, l’état final est donné par $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="80e49-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="80e49-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="80e49-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="80e49-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="80e49-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="80e49-110">Tableau de qubits sur lequel la parité est calculée.</span><span class="sxs-lookup"><span data-stu-id="80e49-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="80e49-111">targetQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="80e49-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="80e49-112">Qubit final dans lequel la parité de « qubits » est XOR.</span><span class="sxs-lookup"><span data-stu-id="80e49-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80e49-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80e49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="80e49-114">Notes</span><span class="sxs-lookup"><span data-stu-id="80e49-114">Remarks</span></span>

<span data-ttu-id="80e49-115">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="80e49-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="80e49-116">and</span><span class="sxs-lookup"><span data-stu-id="80e49-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```