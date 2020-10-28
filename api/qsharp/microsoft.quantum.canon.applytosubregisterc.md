---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Opération ApplyToSubregisterC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704646"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="7e847-102">Opération ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="7e847-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="7e847-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e847-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e847-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e847-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e847-105">Applique une opération à un sous-registre d’un registre, avec qubits spécifié par un tableau de leurs index.</span><span class="sxs-lookup"><span data-stu-id="7e847-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="7e847-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="7e847-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7e847-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="7e847-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="7e847-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e847-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7e847-109">Opération à appliquer à subregister.</span><span class="sxs-lookup"><span data-stu-id="7e847-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="7e847-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7e847-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7e847-111">Tableau d’index, indiquant à quel qubits l’opération sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="7e847-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7e847-112">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7e847-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7e847-113">Inscrivez-vous sur lequel l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="7e847-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e847-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e847-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7e847-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e847-115">See Also</span></span>

- [<span data-ttu-id="7e847-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="7e847-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)