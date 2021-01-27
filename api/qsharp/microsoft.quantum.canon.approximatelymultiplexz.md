---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Opération ApproximatelyMultiplexZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: b69b4de62241a7d16c2f07449115f864defda45d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841085"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="97918-102">Opération ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="97918-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="97918-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="97918-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="97918-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97918-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97918-105">Applique une rotation Pauli Z conditionnée sur un tableau de qubits, ce qui tronque les petits angles de rotation en fonction d’une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="97918-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="97918-106">Description</span><span class="sxs-lookup"><span data-stu-id="97918-106">Description</span></span>

<span data-ttu-id="97918-107">Cela applique l’opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l’opérateur Pauli qubit $Z $ lorsqu’il est contrôlé par l' $n de l’État $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="97918-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="97918-108">En particulier, cette opération peut être représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="97918-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="97918-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="97918-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="97918-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="97918-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="97918-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="97918-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="97918-112">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97918-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97918-113">Tolérance en dessous de laquelle les petits coefficients sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="97918-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="97918-114">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="97918-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="97918-115">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="97918-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="97918-116">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="97918-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="97918-117">contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="97918-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="97918-118">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="97918-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="97918-119">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97918-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97918-120">Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="97918-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97918-121">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97918-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="97918-122">Notes</span><span class="sxs-lookup"><span data-stu-id="97918-122">Remarks</span></span>

<span data-ttu-id="97918-123">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="97918-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="97918-124">Références</span><span class="sxs-lookup"><span data-stu-id="97918-124">References</span></span>

- <span data-ttu-id="97918-125">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="97918-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="97918-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97918-126">See Also</span></span>

- [<span data-ttu-id="97918-127">Microsoft. Quantum. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="97918-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)