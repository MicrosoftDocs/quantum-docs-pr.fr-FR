---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Opération ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218799"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="9240e-102">Opération ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="9240e-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="9240e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9240e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9240e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9240e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9240e-105">Applique l’échange Fermionic.</span><span class="sxs-lookup"><span data-stu-id="9240e-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9240e-106">Description</span><span class="sxs-lookup"><span data-stu-id="9240e-106">Description</span></span>

<span data-ttu-id="9240e-107">Cela échange le qubits tout en appliquant une phase globale de-1 si les deux qubits sont des 1s.</span><span class="sxs-lookup"><span data-stu-id="9240e-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="9240e-108">Préserve l’anti-symmetrization des orbites.</span><span class="sxs-lookup"><span data-stu-id="9240e-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="9240e-109">Voir  pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="9240e-109">See  for more information.</span></span>

<span data-ttu-id="9240e-110">Cette opération est représentée par l’opérateur unitaire \begin{align} f_ {swap} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="9240e-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="9240e-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9240e-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="9240e-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="9240e-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="9240e-113">qubit1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9240e-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9240e-114">Premier qubit à permuter.</span><span class="sxs-lookup"><span data-stu-id="9240e-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="9240e-115">qubit2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9240e-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9240e-116">Deuxième qubit à permuter.</span><span class="sxs-lookup"><span data-stu-id="9240e-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9240e-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9240e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9240e-118">Références</span><span class="sxs-lookup"><span data-stu-id="9240e-118">References</span></span>

- [<span data-ttu-id="9240e-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv : 1706.00023</span><span class="sxs-lookup"><span data-stu-id="9240e-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="9240e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9240e-120">See Also</span></span>

- [<span data-ttu-id="9240e-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="9240e-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)