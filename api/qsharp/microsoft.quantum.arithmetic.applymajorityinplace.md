---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Opération ApplyMajorityInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190732"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="07245-102">Opération ApplyMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="07245-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="07245-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="07245-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="07245-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07245-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07245-105">Applique l’opération de qubit majoritaire sur place sur un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="07245-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="07245-106">Description</span><span class="sxs-lookup"><span data-stu-id="07245-106">Description</span></span>

<span data-ttu-id="07245-107">Cette opération calcule la fonction majoritaire sur place sur 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="07245-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="07245-108">Si vous désignez la sortie qubit comme $z $ et l’entrée qubits $x $ et $y $, l’opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="07245-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="07245-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="07245-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="07245-110">sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07245-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07245-111">Premier qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="07245-111">First input qubit.</span></span> <span data-ttu-id="07245-112">Notez que la sortie est calculée sur place et stockée dans ce qubit.</span><span class="sxs-lookup"><span data-stu-id="07245-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="07245-113">entrée : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="07245-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="07245-114">Deuxième et troisième qubits d’entrée.</span><span class="sxs-lookup"><span data-stu-id="07245-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07245-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07245-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

