---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Opération ApplyMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707595"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="3f360-102">Opération ApplyMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="3f360-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="3f360-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f360-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f360-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f360-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f360-105">Applique l’opération de qubit majoritaire sur place sur un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="3f360-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="3f360-106">Description</span><span class="sxs-lookup"><span data-stu-id="3f360-106">Description</span></span>

<span data-ttu-id="3f360-107">Cette opération calcule la fonction majoritaire sur place sur 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="3f360-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="3f360-108">Si vous désignez la sortie qubit comme $z $ et l’entrée qubits $x $ et $y $, l’opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="3f360-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="3f360-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="3f360-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="3f360-110">sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3f360-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3f360-111">Premier qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="3f360-111">First input qubit.</span></span> <span data-ttu-id="3f360-112">Notez que la sortie est calculée sur place et stockée dans ce qubit.</span><span class="sxs-lookup"><span data-stu-id="3f360-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="3f360-113">entrée : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f360-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f360-114">Deuxième et troisième qubits d’entrée.</span><span class="sxs-lookup"><span data-stu-id="3f360-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f360-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f360-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

