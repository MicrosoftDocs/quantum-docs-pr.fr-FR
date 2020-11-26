---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Opération ApplyLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209313"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="4c2a9-102">Opération ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="4c2a9-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="4c2a9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c2a9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c2a9-105">Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, avec T-depth 1, à l’aide de mesures pour effectuer l’opération joint.</span><span class="sxs-lookup"><span data-stu-id="4c2a9-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4c2a9-106">Description</span><span class="sxs-lookup"><span data-stu-id="4c2a9-106">Description</span></span>

<span data-ttu-id="4c2a9-107">Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.</span><span class="sxs-lookup"><span data-stu-id="4c2a9-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="4c2a9-108">L’opération a T-Count 4, T-depth 1 et requiert un qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.</span><span class="sxs-lookup"><span data-stu-id="4c2a9-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="4c2a9-109">Le voisin de cette opération est basé sur les mesures et ne nécessite pas de grille T, ni de qubit d’assistance.</span><span class="sxs-lookup"><span data-stu-id="4c2a9-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="4c2a9-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="4c2a9-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="4c2a9-111">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4c2a9-112">Premier contrôle qubit</span><span class="sxs-lookup"><span data-stu-id="4c2a9-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="4c2a9-113">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4c2a9-114">Deuxième qubit de contrôle</span><span class="sxs-lookup"><span data-stu-id="4c2a9-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4c2a9-115">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4c2a9-116">Qubit auxiliaire cible ; doit être dans l’État 0</span><span class="sxs-lookup"><span data-stu-id="4c2a9-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c2a9-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c2a9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="4c2a9-118">Références</span><span class="sxs-lookup"><span data-stu-id="4c2a9-118">References</span></span>

- <span data-ttu-id="4c2a9-119">Cody Jones : « nouvelles constructions pour la porte Toffoli à tolérance de pannes », phys. Rev. A 87, 022328, 2013 [arXiv : 1212.5069](https://arxiv.org/abs/1212.5069) doi : 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="4c2a9-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="4c2a9-120">Peter selingo : « circuits quantiques de T-depth 1 », phys. Rev. A 87, 042302, 2013 [arXiv : 1210.0974](https://arxiv.org/abs/1210.0974) doi : 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="4c2a9-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>