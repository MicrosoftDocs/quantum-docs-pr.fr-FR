---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateCP
title: Opération PrepareArbitraryStateCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 21a632c003da16fb5cb20ab97fc0d251a897892b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210639"
---
# <a name="preparearbitrarystatecp-operation"></a><span data-ttu-id="f9578-102">Opération PrepareArbitraryStateCP</span><span class="sxs-lookup"><span data-stu-id="f9578-102">PrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="f9578-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f9578-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f9578-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9578-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9578-105">À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible, prépare un État sur ce registre décrit par les coefficients donnés.</span><span class="sxs-lookup"><span data-stu-id="f9578-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateCP (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f9578-106">Description</span><span class="sxs-lookup"><span data-stu-id="f9578-106">Description</span></span>

<span data-ttu-id="f9578-107">Cette opération prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ à partir de l’état de base de $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f9578-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="f9578-108">En particulier, l’action de cette opération peut être simulée par une transformation unitaire $U $ qui agit sur l’état tous les zéros comme</span><span class="sxs-lookup"><span data-stu-id="f9578-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="f9578-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\Psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="f9578-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="f9578-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f9578-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f9578-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="f9578-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="f9578-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f9578-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="f9578-113">Tableau allant jusqu’à un maximum de $2 ^ n $ de coefficients complexes représentés par leur valeur absolue et la phase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="f9578-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="f9578-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="f9578-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f9578-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9578-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9578-116">Qubit enregistre les États du numéro d’encodage au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="f9578-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="f9578-117">Cette valeur est censée être initialisée dans l’état de la base de calcul $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="f9578-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9578-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9578-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f9578-119">Notes</span><span class="sxs-lookup"><span data-stu-id="f9578-119">Remarks</span></span>

<span data-ttu-id="f9578-120">Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="f9578-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f9578-121">`coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="f9578-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f9578-122">Références</span><span class="sxs-lookup"><span data-stu-id="f9578-122">References</span></span>

- <span data-ttu-id="f9578-123">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f9578-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="f9578-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9578-124">See Also</span></span>

- [<span data-ttu-id="f9578-125">Microsoft. Quantum. PREPARATION. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="f9578-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)