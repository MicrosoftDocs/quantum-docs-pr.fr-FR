---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Opération CompareUsingRippleCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707379"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="45abf-102">Opération CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="45abf-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="45abf-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45abf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45abf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45abf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45abf-105">Cette opération vérifie si un entier représenté par un registre de qubits est supérieur à un autre entier, en appliquant un XOR du résultat dans un qubit de sortie.</span><span class="sxs-lookup"><span data-stu-id="45abf-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="45abf-106">Description</span><span class="sxs-lookup"><span data-stu-id="45abf-106">Description</span></span>

<span data-ttu-id="45abf-107">Étant donné deux entiers `x` et `y` stockés dans des registres qubit de taille égale, cette opération vérifie si elles `x > y` répondent.</span><span class="sxs-lookup"><span data-stu-id="45abf-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="45abf-108">Si la valeur est true, 1 est XOR dans un qubit de sortie.</span><span class="sxs-lookup"><span data-stu-id="45abf-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="45abf-109">Dans le cas contraire, 0 est XOR dans un qubit de sortie.</span><span class="sxs-lookup"><span data-stu-id="45abf-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="45abf-110">En d’autres termes, cette opération peut être représentée par l’unité $ $ \begin{align} U\ket {x} \ Ket {y} \ Ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="45abf-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="45abf-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="45abf-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="45abf-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="45abf-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="45abf-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45abf-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45abf-114">Premier nombre à comparer stocké au `LittleEndian` format dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="45abf-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="45abf-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45abf-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45abf-116">Deuxième nombre à comparer stocké au `LittleEndian` format dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="45abf-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="45abf-117">sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="45abf-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="45abf-118">Qubit qui stocke le résultat de la comparaison $x>y $.</span><span class="sxs-lookup"><span data-stu-id="45abf-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45abf-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45abf-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="45abf-120">Références</span><span class="sxs-lookup"><span data-stu-id="45abf-120">References</span></span>

- <span data-ttu-id="45abf-121">Un nouveau circuit d’addition d’ondulations Quantum, Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="45abf-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>