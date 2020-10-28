---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Opération MultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703960"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="25266-102">Opération MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="25266-102">MultiplexPauli operation</span></span>

<span data-ttu-id="25266-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25266-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25266-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25266-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25266-105">Applique une rotation Pauli conditionnée sur un tableau de qubits.</span><span class="sxs-lookup"><span data-stu-id="25266-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="25266-106">Description</span><span class="sxs-lookup"><span data-stu-id="25266-106">Description</span></span>

<span data-ttu-id="25266-107">Cela s’applique à une opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l' $P opérateur Pauli qubit $ lorsqu’il est contrôlé par le $n l’état de nombre $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="25266-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="25266-108">En particulier, l’action de cette opération est représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="25266-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="25266-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="25266-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="25266-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="25266-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="25266-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="25266-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="25266-112">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="25266-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="25266-113">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="25266-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="25266-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="25266-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="25266-115">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="25266-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="25266-116">Opérateur Pauli $P $ qui détermine l’axe de rotation.</span><span class="sxs-lookup"><span data-stu-id="25266-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="25266-117">contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="25266-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="25266-118">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="25266-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="25266-119">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="25266-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="25266-120">Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="25266-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25266-121">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25266-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="25266-122">Notes</span><span class="sxs-lookup"><span data-stu-id="25266-122">Remarks</span></span>

<span data-ttu-id="25266-123">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="25266-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="25266-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25266-124">See Also</span></span>

- [<span data-ttu-id="25266-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="25266-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)