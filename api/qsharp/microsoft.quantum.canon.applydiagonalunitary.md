---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: Opération ApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705387"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="f7719-102">Opération ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="f7719-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="f7719-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7719-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7719-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7719-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7719-105">Applique un tableau de phases complexes aux États de base numériques d’un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="f7719-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f7719-106">Description</span><span class="sxs-lookup"><span data-stu-id="f7719-106">Description</span></span>

<span data-ttu-id="f7719-107">Cette opération implémente une unité diagonale qui applique une phase complexe $e ^ {i \ theta_j} $ sur le $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="f7719-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="f7719-108">En particulier, cette opération peut être représentée par l’unité</span><span class="sxs-lookup"><span data-stu-id="f7719-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="f7719-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="f7719-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="f7719-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f7719-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f7719-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="f7719-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="f7719-112">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f7719-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f7719-113">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="f7719-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="f7719-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="f7719-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f7719-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7719-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7719-116">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="f7719-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7719-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7719-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7719-118">Notes</span><span class="sxs-lookup"><span data-stu-id="f7719-118">Remarks</span></span>

<span data-ttu-id="f7719-119">`coefficients` sera complété avec les éléments $ \ theta_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="f7719-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f7719-120">Références</span><span class="sxs-lookup"><span data-stu-id="f7719-120">References</span></span>

- <span data-ttu-id="f7719-121">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f7719-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="f7719-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7719-122">See Also</span></span>

- [<span data-ttu-id="f7719-123">Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="f7719-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)