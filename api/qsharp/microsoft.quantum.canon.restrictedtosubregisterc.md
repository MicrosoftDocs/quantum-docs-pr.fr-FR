---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e03f695ea5943bc2296b0ef1ce613f7835a87c5a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205250"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="64e2a-102">RestrictedToSubregisterC fonction)</span><span class="sxs-lookup"><span data-stu-id="64e2a-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="64e2a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64e2a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64e2a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64e2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64e2a-105">Restreint une opération à un tableau d’index d’un registre, c’est-à-dire un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="64e2a-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="64e2a-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="64e2a-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="64e2a-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="64e2a-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="64e2a-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="64e2a-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="64e2a-109">Opération à limiter à un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="64e2a-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="64e2a-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="64e2a-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="64e2a-111">Tableau d’index, indiquant à quel qubits l’opération sera restreinte.</span><span class="sxs-lookup"><span data-stu-id="64e2a-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-ctl"></a><span data-ttu-id="64e2a-112">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="64e2a-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="64e2a-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64e2a-113">See Also</span></span>

- [<span data-ttu-id="64e2a-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="64e2a-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)