---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Opération PermuteQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205600"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="436c0-102">Opération PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="436c0-102">PermuteQubits operation</span></span>

<span data-ttu-id="436c0-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="436c0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="436c0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="436c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="436c0-105">Permute qubits à l’aide de l’opération d’échange.</span><span class="sxs-lookup"><span data-stu-id="436c0-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="436c0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="436c0-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="436c0-107">classement : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="436c0-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="436c0-108">Décrit le nouveau classement du qubits, où qubit à l’index i se trouve maintenant à l’ordre [i].</span><span class="sxs-lookup"><span data-stu-id="436c0-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="436c0-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="436c0-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="436c0-110">Qubit Inscrivez-vous pour être traité.</span><span class="sxs-lookup"><span data-stu-id="436c0-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="436c0-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="436c0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

