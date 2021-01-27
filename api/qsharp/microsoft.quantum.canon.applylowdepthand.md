---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Opération ApplyLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841702"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="2d113-102">Opération ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="2d113-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="2d113-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2d113-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2d113-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d113-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d113-105">Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, avec T-depth 1, à l’aide de mesures pour effectuer l’opération joint.</span><span class="sxs-lookup"><span data-stu-id="2d113-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2d113-106">Description</span><span class="sxs-lookup"><span data-stu-id="2d113-106">Description</span></span>

<span data-ttu-id="2d113-107">Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.</span><span class="sxs-lookup"><span data-stu-id="2d113-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="2d113-108">L’opération a T-Count 4, T-depth 1 et requiert un qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.</span><span class="sxs-lookup"><span data-stu-id="2d113-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="2d113-109">Le voisin de cette opération est basé sur les mesures et ne nécessite pas de grille T, ni de qubit d’assistance.</span><span class="sxs-lookup"><span data-stu-id="2d113-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="2d113-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="2d113-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="2d113-111">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d113-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d113-112">Premier contrôle qubit</span><span class="sxs-lookup"><span data-stu-id="2d113-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="2d113-113">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d113-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d113-114">Deuxième qubit de contrôle</span><span class="sxs-lookup"><span data-stu-id="2d113-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2d113-115">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d113-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d113-116">Qubit auxiliaire cible ; doit être dans l’État 0</span><span class="sxs-lookup"><span data-stu-id="2d113-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d113-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d113-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2d113-118">Références</span><span class="sxs-lookup"><span data-stu-id="2d113-118">References</span></span>

- <span data-ttu-id="2d113-119">Cody Jones : « nouvelles constructions pour la porte Toffoli à tolérance de pannes », phys. Rev. A 87, 022328, 2013 [arXiv : 1212.5069](https://arxiv.org/abs/1212.5069) doi : 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="2d113-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="2d113-120">Peter selingo : « circuits quantiques de T-depth 1 », phys. Rev. A 87, 042302, 2013 [arXiv : 1210.0974](https://arxiv.org/abs/1210.0974) doi : 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="2d113-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>