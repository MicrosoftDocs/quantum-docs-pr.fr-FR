---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Opération ApplyPermutationUsingDecomposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192126"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="f386a-102">Opération ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="f386a-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="f386a-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f386a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f386a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f386a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f386a-105">Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la décomposition.</span><span class="sxs-lookup"><span data-stu-id="f386a-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f386a-106">Description</span><span class="sxs-lookup"><span data-stu-id="f386a-106">Description</span></span>

<span data-ttu-id="f386a-107">Cette procédure implémente l’approche de synthèse basée sur la décomposition.</span><span class="sxs-lookup"><span data-stu-id="f386a-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="f386a-108">L’entrée est une permutation de $ \pi $ sur $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, qui représente une fonction booléenne réversible $n $-variable.</span><span class="sxs-lookup"><span data-stu-id="f386a-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="f386a-109">L’algorithme exécute itérativement les étapes suivantes pour chaque index de variable $i $ :</span><span class="sxs-lookup"><span data-stu-id="f386a-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="f386a-110">Compute $ ((\ pi_l, \ pi_r), \pi') $, de telle sorte que les images de $ \ pi_l $ et $ \ pi_r $ ne changent pas les bits dans leurs éléments à des index autres que $i $ et les images de $ \pi' $ ne changent pas le bit $i $ dans leurs éléments.</span><span class="sxs-lookup"><span data-stu-id="f386a-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="f386a-111">Définissez $ \pi \leftarrow \pi' $ et dérivez les tables de vérité de $ \ pi_l $ et $ \ pi_r $ en fonction des éléments qui ne sont pas des points fixes.</span><span class="sxs-lookup"><span data-stu-id="f386a-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="f386a-112">Après l’application de ces étapes pour tous les index de variable, la permutation restante $ \pi $ sera l’identité, et en fonction des tables et des index de vérité collectés, vous pouvez appliquer des opérations contrôlées de table de vérité @"microsoft.quantum.intrinsic.x" à l’aide de l' @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" opération.</span><span class="sxs-lookup"><span data-stu-id="f386a-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="f386a-113">L’ordre des variables est $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="f386a-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="f386a-114">Un ordre de variable personnalisé peut être spécifié dans l’opération @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="f386a-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="f386a-115">Entrée</span><span class="sxs-lookup"><span data-stu-id="f386a-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="f386a-116">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f386a-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f386a-117">Permutation de $2 ^ n $ Elements à partir de 0.</span><span class="sxs-lookup"><span data-stu-id="f386a-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f386a-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f386a-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f386a-119">Liste de $n $ qubits à laquelle la permutation est appliquée.</span><span class="sxs-lookup"><span data-stu-id="f386a-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f386a-120">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f386a-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f386a-121">Références</span><span class="sxs-lookup"><span data-stu-id="f386a-121">References</span></span>

- [<span data-ttu-id="f386a-122">*Alexis de vos*, *Yvan van Rentergem*, ADV. in Math. of comm. 2 (2), 2008, pp. 183--200</span><span class="sxs-lookup"><span data-stu-id="f386a-122">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="f386a-123">*Mathias Soeken*, *Laura tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of symbolal Computing 73 (2016), pp. 1--26</span><span class="sxs-lookup"><span data-stu-id="f386a-123">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="f386a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f386a-124">See Also</span></span>

- [<span data-ttu-id="f386a-125">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="f386a-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="f386a-126">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="f386a-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)