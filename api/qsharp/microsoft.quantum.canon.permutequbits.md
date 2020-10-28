---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Opération PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703906"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="7635a-102">Opération PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="7635a-102">PermuteQubits operation</span></span>

<span data-ttu-id="7635a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7635a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7635a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7635a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7635a-105">Permute qubits à l’aide de l’opération d’échange.</span><span class="sxs-lookup"><span data-stu-id="7635a-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7635a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7635a-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="7635a-107">classement : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7635a-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7635a-108">Décrit le nouveau classement du qubits, où qubit à l’index i se trouve maintenant à l’ordre [i].</span><span class="sxs-lookup"><span data-stu-id="7635a-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="7635a-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7635a-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7635a-110">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="7635a-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7635a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7635a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

