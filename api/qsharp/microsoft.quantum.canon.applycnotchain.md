---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Opération ApplyCNOTChain
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219139"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="f1fe1-102">Opération ApplyCNOTChain</span><span class="sxs-lookup"><span data-stu-id="f1fe1-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="f1fe1-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1fe1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1fe1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1fe1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1fe1-105">Calcule la parité d’un registre de qubits sur place.</span><span class="sxs-lookup"><span data-stu-id="f1fe1-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f1fe1-106">Description</span><span class="sxs-lookup"><span data-stu-id="f1fe1-106">Description</span></span>

<span data-ttu-id="f1fe1-107">Cette opération transforme l’état de son entrée sous la forme $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="f1fe1-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="f1fe1-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f1fe1-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f1fe1-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="f1fe1-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="f1fe1-110">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1fe1-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1fe1-111">Tableau de qubits dont la parité doit être calculée et stockée.</span><span class="sxs-lookup"><span data-stu-id="f1fe1-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1fe1-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1fe1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

