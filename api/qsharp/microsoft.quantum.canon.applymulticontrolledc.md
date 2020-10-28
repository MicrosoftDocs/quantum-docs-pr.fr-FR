---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Opération ApplyMultiControlledC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 36010ba667190c237b64f60b7246010199a8ba1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705198"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="395e5-102">Opération ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="395e5-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="395e5-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="395e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="395e5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="395e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="395e5-105">Applique une version contrôlée par multiplication d’une opération contrôlée de façon unique.</span><span class="sxs-lookup"><span data-stu-id="395e5-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="395e5-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="395e5-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="395e5-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="395e5-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="395e5-108">singlyControlledOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="395e5-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="395e5-109">Opération contrôlée sur un qubit unique.</span><span class="sxs-lookup"><span data-stu-id="395e5-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="395e5-110">Le premier qubit de l’argument de l’opération est supposé être un contrôle et les autres sont supposés être des qubits cibles.</span><span class="sxs-lookup"><span data-stu-id="395e5-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="395e5-111">`ApplyMultiControlled` appelle toujours `singlyControlledOp` avec un argument de longueur au moins égal à 1.</span><span class="sxs-lookup"><span data-stu-id="395e5-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="395e5-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="395e5-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="395e5-113">Porte contrôlée par contrôle-non à utiliser pour la construction.</span><span class="sxs-lookup"><span data-stu-id="395e5-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="395e5-114">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="395e5-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="395e5-115">Qubits `singlyControlledOp` à contrôler sur.</span><span class="sxs-lookup"><span data-stu-id="395e5-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="395e5-116">La longueur de `controls` doit être au moins égale à 1.</span><span class="sxs-lookup"><span data-stu-id="395e5-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="395e5-117">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="395e5-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="395e5-118">Qubits cible sur lequel `singlyControlledOp` agit.</span><span class="sxs-lookup"><span data-stu-id="395e5-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="395e5-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="395e5-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="395e5-120">Notes</span><span class="sxs-lookup"><span data-stu-id="395e5-120">Remarks</span></span>

<span data-ttu-id="395e5-121">Cette opération utilise uniquement Clean Ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="395e5-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="395e5-122">Pour l’explication et le schéma du circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="395e5-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="395e5-123">Références</span><span class="sxs-lookup"><span data-stu-id="395e5-123">References</span></span>

- [<span data-ttu-id="395e5-124">*Michael A. Nielsen, Isaac L. Chuang* , calcul quantique et informations Quantum</span><span class="sxs-lookup"><span data-stu-id="395e5-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="395e5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="395e5-125">See Also</span></span>

- [<span data-ttu-id="395e5-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="395e5-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)