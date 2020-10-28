---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Opération ApproximatelyMultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704539"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="bdf19-102">Opération ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="bdf19-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="bdf19-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdf19-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdf19-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdf19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdf19-105">Applique une rotation Pauli conditionnée sur un tableau de qubits, ce qui tronque les petits angles de rotation en fonction d’une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="bdf19-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="bdf19-106">Description</span><span class="sxs-lookup"><span data-stu-id="bdf19-106">Description</span></span>

<span data-ttu-id="bdf19-107">Cela s’applique à une opération unitaire contrôlée par multiplication qui effectue des rotations par angle $ \ theta_j $ à propos de l' $P opérateur Pauli qubit $ lorsqu’il est contrôlé par le $n l’état de nombre $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="bdf19-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="bdf19-108">En particulier, l’action de cette opération est représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="bdf19-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="bdf19-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="bdf19-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="bdf19-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="bdf19-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="bdf19-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="bdf19-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="bdf19-112">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bdf19-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bdf19-113">Tolérance en dessous de laquelle les petits coefficients sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="bdf19-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="bdf19-114">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bdf19-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bdf19-115">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="bdf19-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="bdf19-116">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="bdf19-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="bdf19-117">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="bdf19-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="bdf19-118">Opérateur Pauli $P $ qui détermine l’axe de rotation.</span><span class="sxs-lookup"><span data-stu-id="bdf19-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="bdf19-119">contrôle : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bdf19-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bdf19-120">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="bdf19-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bdf19-121">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bdf19-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bdf19-122">Registre qubit unique qui est pivoté par $e ^ {i P theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="bdf19-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdf19-123">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdf19-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bdf19-124">Notes</span><span class="sxs-lookup"><span data-stu-id="bdf19-124">Remarks</span></span>

<span data-ttu-id="bdf19-125">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="bdf19-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdf19-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdf19-126">See Also</span></span>

- [<span data-ttu-id="bdf19-127">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="bdf19-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)