---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Opération ApplyToSubregisterCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9f24c3ca9b152cf9bbf81e59b86f83a0ab459031
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841210"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="c8ac1-102">Opération ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="c8ac1-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="c8ac1-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8ac1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8ac1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8ac1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8ac1-105">Applique une opération à un sous-registre d’un registre, avec qubits spécifié par un tableau de leurs index.</span><span class="sxs-lookup"><span data-stu-id="c8ac1-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="c8ac1-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="c8ac1-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c8ac1-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c8ac1-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c8ac1-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c8ac1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8ac1-109">Opération à appliquer à subregister.</span><span class="sxs-lookup"><span data-stu-id="c8ac1-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="c8ac1-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c8ac1-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c8ac1-111">Tableau d’index, indiquant à quel qubits l’opération sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="c8ac1-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c8ac1-112">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c8ac1-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c8ac1-113">Inscrivez-vous sur lequel l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="c8ac1-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8ac1-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8ac1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c8ac1-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8ac1-115">See Also</span></span>

- [<span data-ttu-id="c8ac1-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="c8ac1-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)