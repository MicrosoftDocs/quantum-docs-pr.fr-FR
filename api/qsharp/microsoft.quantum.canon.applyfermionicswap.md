---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Opération ApplyFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705379"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="ecf4d-102">Opération ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="ecf4d-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="ecf4d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ecf4d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ecf4d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecf4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecf4d-105">Applique l’échange Fermionic.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ecf4d-106">Description</span><span class="sxs-lookup"><span data-stu-id="ecf4d-106">Description</span></span>

<span data-ttu-id="ecf4d-107">Cela échange le qubits tout en appliquant une phase globale de-1 si les deux qubits sont des 1s.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="ecf4d-108">Préserve l’anti-symmetrization des orbites.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="ecf4d-109">Voir  pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-109">See  for more information.</span></span>

<span data-ttu-id="ecf4d-110">Cette opération est représentée par l’opérateur unitaire \begin{align} f_ {swap} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="ecf4d-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ecf4d-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="ecf4d-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="ecf4d-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="ecf4d-113">qubit1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ecf4d-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ecf4d-114">Premier qubit à permuter.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="ecf4d-115">qubit2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ecf4d-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ecf4d-116">Deuxième qubit à permuter.</span><span class="sxs-lookup"><span data-stu-id="ecf4d-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ecf4d-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecf4d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ecf4d-118">Références</span><span class="sxs-lookup"><span data-stu-id="ecf4d-118">References</span></span>

- [<span data-ttu-id="ecf4d-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv : 1706.00023</span><span class="sxs-lookup"><span data-stu-id="ecf4d-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="ecf4d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecf4d-120">See Also</span></span>

- [<span data-ttu-id="ecf4d-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="ecf4d-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)