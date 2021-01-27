---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Opération PrepareArbitraryState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: e2e4818e5d30b17dd1984c36da92d76b84403e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842386"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="3d8ae-102">Opération PrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="3d8ae-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="3d8ae-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3d8ae-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3d8ae-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d8ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="3d8ae-105">PrepareArbitraryState est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="3d8ae-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="3d8ae-107">À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible, prépare un État sur ce registre décrit par les coefficients donnés.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3d8ae-108">Description</span><span class="sxs-lookup"><span data-stu-id="3d8ae-108">Description</span></span>

<span data-ttu-id="3d8ae-109">Cette opération prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ à partir de l’état de base de $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="3d8ae-110">En particulier, l’action de cette opération peut être simulée par une transformation unitaire $U $ qui agit sur l’état tous les zéros comme</span><span class="sxs-lookup"><span data-stu-id="3d8ae-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="3d8ae-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\Psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="3d8ae-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3d8ae-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="3d8ae-113">Entrée</span><span class="sxs-lookup"><span data-stu-id="3d8ae-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="3d8ae-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="3d8ae-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="3d8ae-115">Tableau allant jusqu’à un maximum de $2 ^ n $ de coefficients complexes représentés par leur valeur absolue et la phase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="3d8ae-116">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3d8ae-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3d8ae-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3d8ae-118">Qubit enregistre les États du numéro d’encodage au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="3d8ae-119">Cette valeur est censée être initialisée dans l’état de la base de calcul $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d8ae-120">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d8ae-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3d8ae-121">Notes</span><span class="sxs-lookup"><span data-stu-id="3d8ae-121">Remarks</span></span>

<span data-ttu-id="3d8ae-122">Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="3d8ae-123">`coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="3d8ae-124">Références</span><span class="sxs-lookup"><span data-stu-id="3d8ae-124">References</span></span>

- <span data-ttu-id="3d8ae-125">Synthèse des circuits logiques quantiques Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="3d8ae-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="3d8ae-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d8ae-126">See Also</span></span>

- [<span data-ttu-id="3d8ae-127">Microsoft. Quantum. PREPARATION. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="3d8ae-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)