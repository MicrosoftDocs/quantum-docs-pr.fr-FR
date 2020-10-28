---
uid: Microsoft.Quantum.Canon.AndLadder
title: Opération AndLadder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705518"
---
# <a name="andladder-operation"></a><span data-ttu-id="07247-102">Opération AndLadder</span><span class="sxs-lookup"><span data-stu-id="07247-102">AndLadder operation</span></span>

<span data-ttu-id="07247-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07247-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07247-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07247-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07247-105">Effectue une « échelle » contrôlée sur un registre de qubits cibles.</span><span class="sxs-lookup"><span data-stu-id="07247-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="07247-106">Description</span><span class="sxs-lookup"><span data-stu-id="07247-106">Description</span></span>

<span data-ttu-id="07247-107">Cette opération applique une transformation décrite par le mappage suivant de la base de calcul, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x \_ n} $ fait référence aux États de base de calcul de `controls` , et où $ \ket{y \_ 1, \dots, y \_ {n-1}} $ fait référence aux États de base de calcul de `targets` .</span><span class="sxs-lookup"><span data-stu-id="07247-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="07247-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="07247-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="07247-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="07247-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="07247-110">Porte CCNOT à utiliser pour la construction.</span><span class="sxs-lookup"><span data-stu-id="07247-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="07247-111">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="07247-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="07247-112">Un registre de qubits à utiliser comme contrôles pour l’échelle et.</span><span class="sxs-lookup"><span data-stu-id="07247-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="07247-113">Cette opération laisse les États de base de calcul `controls` invariants.</span><span class="sxs-lookup"><span data-stu-id="07247-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="07247-114">La longueur de `controls` doit être au moins égale à 2, et doit être égale à un plus la longueur de `targets` .</span><span class="sxs-lookup"><span data-stu-id="07247-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="07247-115">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="07247-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="07247-116">La longueur de `targets` doit être au moins égale à 1 et égale à la longueur de `controls` moins un.</span><span class="sxs-lookup"><span data-stu-id="07247-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07247-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07247-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07247-118">Notes</span><span class="sxs-lookup"><span data-stu-id="07247-118">Remarks</span></span>

- <span data-ttu-id="07247-119">Utilisé dans le cadre de <xref:microsoft.quantum.canon.applymulticontrolledc> et de <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="07247-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="07247-120">Pour le diagramme explication et circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="07247-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="07247-121">Références</span><span class="sxs-lookup"><span data-stu-id="07247-121">References</span></span>

- [<span data-ttu-id="07247-122">*Michael A. Nielsen, Isaac L. Chuang* , calcul quantique et informations Quantum</span><span class="sxs-lookup"><span data-stu-id="07247-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)