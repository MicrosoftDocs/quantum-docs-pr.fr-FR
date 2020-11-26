---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Opération MultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: 364d23a0e57a2510f069b6db66b085368f20162e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206066"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="a49e8-102">Opération MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="a49e8-102">MultiplexZ operation</span></span>

<span data-ttu-id="a49e8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a49e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a49e8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a49e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a49e8-105">Applique une rotation Pauli Z conditionnée sur un tableau de qubits.</span><span class="sxs-lookup"><span data-stu-id="a49e8-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a49e8-106">Description</span><span class="sxs-lookup"><span data-stu-id="a49e8-106">Description</span></span>

<span data-ttu-id="a49e8-107">Cela applique l’opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l’opérateur Pauli qubit $Z $ lorsqu’il est contrôlé par l' $n de l’État $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="a49e8-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="a49e8-108">En particulier, cette opération peut être représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="a49e8-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="a49e8-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="a49e8-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="a49e8-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a49e8-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a49e8-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="a49e8-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a49e8-112">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a49e8-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a49e8-113">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="a49e8-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="a49e8-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="a49e8-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="a49e8-115">contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a49e8-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a49e8-116">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="a49e8-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a49e8-117">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a49e8-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a49e8-118">Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="a49e8-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a49e8-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a49e8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a49e8-120">Notes</span><span class="sxs-lookup"><span data-stu-id="a49e8-120">Remarks</span></span>

<span data-ttu-id="a49e8-121">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="a49e8-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="a49e8-122">Références</span><span class="sxs-lookup"><span data-stu-id="a49e8-122">References</span></span>

- <span data-ttu-id="a49e8-123">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="a49e8-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="a49e8-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a49e8-124">See Also</span></span>

- [<span data-ttu-id="a49e8-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="a49e8-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)