---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Opération ApplyMultiControlledCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841691"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="ae279-102">Opération ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="ae279-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="ae279-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae279-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae279-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae279-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae279-105">Applique une version contrôlée par multiplication d’une opération contrôlée de façon unique.</span><span class="sxs-lookup"><span data-stu-id="ae279-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="ae279-106">Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="ae279-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ae279-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="ae279-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="ae279-108">singlyControlledOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="ae279-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ae279-109">Opération contrôlée sur un qubit unique.</span><span class="sxs-lookup"><span data-stu-id="ae279-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="ae279-110">Le premier qubit de l’argument de l’opération est supposé être un contrôle et le reste est supposé être qubits cible.</span><span class="sxs-lookup"><span data-stu-id="ae279-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="ae279-111">`ApplyMultiControlled` appelle toujours `singlyControlledOp` avec un argument de longueur au moins égal à 1.</span><span class="sxs-lookup"><span data-stu-id="ae279-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="ae279-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="ae279-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="ae279-113">Porte contrôlée par contrôle-non à utiliser pour la construction.</span><span class="sxs-lookup"><span data-stu-id="ae279-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="ae279-114">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ae279-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ae279-115">Qubits `singlyControlledOp` à contrôler sur.</span><span class="sxs-lookup"><span data-stu-id="ae279-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="ae279-116">La longueur de `controls` doit être au moins égale à 1.</span><span class="sxs-lookup"><span data-stu-id="ae279-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="ae279-117">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ae279-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ae279-118">Qubits cible sur lequel `singlyControlledOp` agit.</span><span class="sxs-lookup"><span data-stu-id="ae279-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae279-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae279-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ae279-120">Notes</span><span class="sxs-lookup"><span data-stu-id="ae279-120">Remarks</span></span>

<span data-ttu-id="ae279-121">Cette opération utilise uniquement Clean Ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="ae279-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="ae279-122">Pour l’explication et le schéma du circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="ae279-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="ae279-123">Références</span><span class="sxs-lookup"><span data-stu-id="ae279-123">References</span></span>

- [<span data-ttu-id="ae279-124">*Michael A. Nielsen, Isaac L. Chuang*, calcul quantique et informations Quantum</span><span class="sxs-lookup"><span data-stu-id="ae279-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="ae279-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae279-125">See Also</span></span>

- [<span data-ttu-id="ae279-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="ae279-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)