---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Opération ApplyToSubregisterA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704659"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="56e31-102">Opération ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="56e31-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="56e31-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56e31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56e31-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56e31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56e31-105">Applique une opération à un sous-registre d’un registre, avec qubits spécifié par un tableau de leurs index.</span><span class="sxs-lookup"><span data-stu-id="56e31-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="56e31-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="56e31-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="56e31-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="56e31-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="56e31-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56e31-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="56e31-109">Opération à appliquer à subregister.</span><span class="sxs-lookup"><span data-stu-id="56e31-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="56e31-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="56e31-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="56e31-111">Tableau d’index, indiquant à quel qubits l’opération sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="56e31-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="56e31-112">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="56e31-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="56e31-113">Inscrivez-vous sur lequel l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="56e31-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56e31-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56e31-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="56e31-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56e31-115">See Also</span></span>

- [<span data-ttu-id="56e31-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="56e31-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)