---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Opération ApproximatelyApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704542"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="8d543-102">Opération ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="8d543-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="8d543-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d543-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d543-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d543-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d543-105">Applique un tableau de phases complexes aux États de base numériques d’un registre de qubits, en tronquant les petits angles de rotation en fonction d’une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="8d543-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8d543-106">Description</span><span class="sxs-lookup"><span data-stu-id="8d543-106">Description</span></span>

<span data-ttu-id="8d543-107">Cette opération implémente une unité diagonale qui applique une phase complexe $e ^ {i \ theta_j} $ sur le $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="8d543-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="8d543-108">En particulier, cette opération peut être représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="8d543-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="8d543-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="8d543-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="8d543-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8d543-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8d543-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="8d543-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="8d543-112">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8d543-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8d543-113">Tolérance en dessous de laquelle les petits coefficients sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="8d543-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="8d543-114">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8d543-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8d543-115">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="8d543-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="8d543-116">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="8d543-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="8d543-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8d543-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8d543-118">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="8d543-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d543-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d543-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d543-120">Notes</span><span class="sxs-lookup"><span data-stu-id="8d543-120">Remarks</span></span>

<span data-ttu-id="8d543-121">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="8d543-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="8d543-122">Références</span><span class="sxs-lookup"><span data-stu-id="8d543-122">References</span></span>

- <span data-ttu-id="8d543-123">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="8d543-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="8d543-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d543-124">See Also</span></span>

- [<span data-ttu-id="8d543-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="8d543-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)