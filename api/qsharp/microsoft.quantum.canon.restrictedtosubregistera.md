---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 28128641a95c6948b5fa5730bf3bd90aa6bb1ef5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205284"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="ef874-102">RestrictedToSubregisterA fonction)</span><span class="sxs-lookup"><span data-stu-id="ef874-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="ef874-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef874-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef874-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef874-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef874-105">Restreint une opération à un tableau d’index d’un registre, c’est-à-dire un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="ef874-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="ef874-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="ef874-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="ef874-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="ef874-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="ef874-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="ef874-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ef874-109">Opération à limiter à un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="ef874-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="ef874-110">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ef874-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ef874-111">Tableau d’index, indiquant à quel qubits l’opération sera restreinte.</span><span class="sxs-lookup"><span data-stu-id="ef874-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-adj"></a><span data-ttu-id="ef874-112">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="ef874-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="ef874-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef874-113">See Also</span></span>

- [<span data-ttu-id="ef874-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="ef874-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)