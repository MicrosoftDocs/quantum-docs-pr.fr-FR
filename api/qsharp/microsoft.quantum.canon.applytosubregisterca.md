---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Opération ApplyToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704638"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="67fce-102">Opération ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="67fce-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="67fce-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67fce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67fce-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67fce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67fce-105">Applique une opération à un sous-registre d’un registre, avec qubits spécifié par un tableau de leurs index.</span><span class="sxs-lookup"><span data-stu-id="67fce-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="67fce-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="67fce-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="67fce-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="67fce-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="67fce-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="67fce-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="67fce-109">Opération à appliquer à subregister.</span><span class="sxs-lookup"><span data-stu-id="67fce-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="67fce-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="67fce-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="67fce-111">Tableau d’index, indiquant à quel qubits l’opération sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="67fce-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="67fce-112">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="67fce-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="67fce-113">Inscrivez-vous sur lequel l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="67fce-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67fce-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67fce-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="67fce-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67fce-115">See Also</span></span>

- [<span data-ttu-id="67fce-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="67fce-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)