---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: Opération ApproximatelyPrepareArbitraryState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708687"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="3021e-102">Opération ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="3021e-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="3021e-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3021e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3021e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3021e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3021e-105">À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible, prépare un État sur ce registre décrit par les coefficients donnés, jusqu’à une tolérance de l’approximation donnée.</span><span class="sxs-lookup"><span data-stu-id="3021e-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="3021e-106">Description</span><span class="sxs-lookup"><span data-stu-id="3021e-106">Description</span></span>

<span data-ttu-id="3021e-107">Cette opération prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ à partir de l’état de base de $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="3021e-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="3021e-108">En particulier, l’action de cette opération peut être simulée par une transformation unitaire $U $ qui agit sur l’état tous les zéros comme</span><span class="sxs-lookup"><span data-stu-id="3021e-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="3021e-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\Psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="3021e-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="3021e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3021e-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="3021e-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="3021e-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="3021e-112">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3021e-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3021e-113">Tolérance approximative à utiliser lors de la préparation de l’État donné.</span><span class="sxs-lookup"><span data-stu-id="3021e-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="3021e-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="3021e-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="3021e-115">Tableau allant jusqu’à un maximum de $2 ^ n $ de coefficients complexes représentés par leur valeur absolue et la phase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="3021e-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="3021e-116">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="3021e-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3021e-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3021e-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3021e-118">Qubit enregistre les États du numéro d’encodage au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="3021e-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="3021e-119">Cette valeur est censée être initialisée dans l’état de la base de calcul $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="3021e-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3021e-120">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3021e-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3021e-121">Notes</span><span class="sxs-lookup"><span data-stu-id="3021e-121">Remarks</span></span>

<span data-ttu-id="3021e-122">Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="3021e-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="3021e-123">`coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3021e-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="3021e-124">Références</span><span class="sxs-lookup"><span data-stu-id="3021e-124">References</span></span>

- <span data-ttu-id="3021e-125">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="3021e-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="3021e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3021e-126">See Also</span></span>

- [<span data-ttu-id="3021e-127">Microsoft. Quantum. PREPARATION. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="3021e-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)