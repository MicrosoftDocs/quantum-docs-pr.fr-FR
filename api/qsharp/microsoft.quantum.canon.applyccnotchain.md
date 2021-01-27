---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Opération ApplyCCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845135"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="490a9-102">Opération ApplyCCNOTChain</span><span class="sxs-lookup"><span data-stu-id="490a9-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="490a9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="490a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="490a9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="490a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="490a9-105">Implémente une cascade de portes CCNOT contrôlées sur les bits correspondants de deux registres qubit, agissant sur la qubit suivante de l’un des registres.</span><span class="sxs-lookup"><span data-stu-id="490a9-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="490a9-106">À partir de qubits à la position 0 dans les deux registres en tant que contrôles, CCNOT est appliqué au qubit à la position 1 du Registre cible, puis contrôlé par le qubits à la position 1 agissant sur le qubit à la position 2 dans le registre cible, etc., se terminant par une action sur le qubit cible à la position 2 `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="490a9-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="490a9-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="490a9-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="490a9-108">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="490a9-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="490a9-109">Registre qubit, utilisé uniquement pour les contrôles.</span><span class="sxs-lookup"><span data-stu-id="490a9-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="490a9-110">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="490a9-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="490a9-111">Registre qubit, utilisé pour les contrôles et comme cible.</span><span class="sxs-lookup"><span data-stu-id="490a9-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="490a9-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="490a9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="490a9-113">Notes</span><span class="sxs-lookup"><span data-stu-id="490a9-113">Remarks</span></span>

<span data-ttu-id="490a9-114">Le registre qubit cible doit avoir un qubit de plus que l’autre.</span><span class="sxs-lookup"><span data-stu-id="490a9-114">The target qubit register must have one qubit more than the other register.</span></span>