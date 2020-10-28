---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Opération ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705195"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="6c73e-102">Opération ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="6c73e-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="6c73e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c73e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c73e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c73e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c73e-105">Applique une version contrôlée par multiplication d’une opération contrôlée de façon unique.</span><span class="sxs-lookup"><span data-stu-id="6c73e-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="6c73e-106">Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="6c73e-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6c73e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="6c73e-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="6c73e-108">singlyControlledOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c73e-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6c73e-109">Opération contrôlée sur un qubit unique.</span><span class="sxs-lookup"><span data-stu-id="6c73e-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="6c73e-110">Le premier qubit de l’argument de l’opération est supposé être un contrôle et le reste est supposé être qubits cible.</span><span class="sxs-lookup"><span data-stu-id="6c73e-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="6c73e-111">`ApplyMultiControlled` appelle toujours `singlyControlledOp` avec un argument de longueur au moins égal à 1.</span><span class="sxs-lookup"><span data-stu-id="6c73e-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="6c73e-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="6c73e-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="6c73e-113">Porte contrôlée par contrôle-non à utiliser pour la construction.</span><span class="sxs-lookup"><span data-stu-id="6c73e-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="6c73e-114">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6c73e-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6c73e-115">Qubits `singlyControlledOp` à contrôler sur.</span><span class="sxs-lookup"><span data-stu-id="6c73e-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="6c73e-116">La longueur de `controls` doit être au moins égale à 1.</span><span class="sxs-lookup"><span data-stu-id="6c73e-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="6c73e-117">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6c73e-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6c73e-118">Qubits cible sur lequel `singlyControlledOp` agit.</span><span class="sxs-lookup"><span data-stu-id="6c73e-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c73e-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c73e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6c73e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="6c73e-120">Remarks</span></span>

<span data-ttu-id="6c73e-121">Cette opération utilise uniquement Clean Ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="6c73e-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="6c73e-122">Pour l’explication et le schéma du circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="6c73e-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="6c73e-123">Références</span><span class="sxs-lookup"><span data-stu-id="6c73e-123">References</span></span>

- [<span data-ttu-id="6c73e-124">*Michael A. Nielsen, Isaac L. Chuang* , calcul quantique et informations Quantum</span><span class="sxs-lookup"><span data-stu-id="6c73e-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="6c73e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c73e-125">See Also</span></span>

- [<span data-ttu-id="6c73e-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="6c73e-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)