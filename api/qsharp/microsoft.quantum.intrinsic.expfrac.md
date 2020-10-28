---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Opération ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702118"
---
# <a name="expfrac-operation"></a><span data-ttu-id="de19d-102">Opération ExpFrac</span><span class="sxs-lookup"><span data-stu-id="de19d-102">ExpFrac operation</span></span>

<span data-ttu-id="de19d-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="de19d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="de19d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de19d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de19d-105">Applique l’exponentiel d’un opérateur Pauli qubit avec un argument donné par une fraction dyadic.</span><span class="sxs-lookup"><span data-stu-id="de19d-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="de19d-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} où $P _i $ est le $i élément $ Th de `paulis` , et où $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="de19d-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="de19d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="de19d-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="de19d-108">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="de19d-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="de19d-109">Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="de19d-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="de19d-110">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de19d-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de19d-111">Numérateur ($k $) dans la représentation dyadic de la fraction de l’angle par lequel le registre qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="de19d-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="de19d-112">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de19d-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de19d-113">Puissance de deux ($n $) spécifiant le dénominateur de l’angle par lequel le registre qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="de19d-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="de19d-114">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de19d-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="de19d-115">Inscrivez-vous pour appliquer la rotation donnée à.</span><span class="sxs-lookup"><span data-stu-id="de19d-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de19d-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de19d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

