---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a49b15ac9c3ba9c1959bdead11549c1f37caabf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205369"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="7a724-102">RestrictedToSubregister fonction)</span><span class="sxs-lookup"><span data-stu-id="7a724-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="7a724-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a724-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a724-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a724-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a724-105">Restreint une opération à un tableau d’index d’un registre, c’est-à-dire un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="7a724-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="7a724-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7a724-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="7a724-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a724-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7a724-108">Opération à limiter à un sous-registre.</span><span class="sxs-lookup"><span data-stu-id="7a724-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="7a724-109">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7a724-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7a724-110">Tableau d’index, indiquant à quel qubits l’opération sera restreinte.</span><span class="sxs-lookup"><span data-stu-id="7a724-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="7a724-111">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a724-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="7a724-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a724-112">See Also</span></span>

- [<span data-ttu-id="7a724-113">Microsoft. Quantum. Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="7a724-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="7a724-114">Microsoft. Quantum. Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="7a724-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="7a724-115">Microsoft. Quantum. Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="7a724-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)