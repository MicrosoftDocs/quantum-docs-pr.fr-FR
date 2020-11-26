---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Opération ApplyPermutationUsingTransformation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192058"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="6e6a0-102">Opération ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="6e6a0-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="6e6a0-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6e6a0-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6e6a0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e6a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e6a0-105">Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la transformation.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6e6a0-106">Description</span><span class="sxs-lookup"><span data-stu-id="6e6a0-106">Description</span></span>

<span data-ttu-id="6e6a0-107">Cette procédure implémente l’approche de synthèse basée sur la transformation unidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="6e6a0-108">L’entrée est une permutation de $ \pi $ sur $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, qui représente une fonction booléenne réversible $n variable $.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="6e6a0-109">L’algorithme effectue itérativement les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e6a0-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="6e6a0-110">Recherchez la plus petite $x $, par exemple $x \ne \pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="6e6a0-111">Recherche des opérations Toffoli à plusieurs contrôleurs, qui s’appliquent aux sorties, à savoir $ \pi (x) = x $ et ne modifient pas $ \pi (x') $ pour tous les $x' < x $</span><span class="sxs-lookup"><span data-stu-id="6e6a0-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="6e6a0-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="6e6a0-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="6e6a0-113">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6e6a0-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6e6a0-114">Permutation de $2 ^ n $ Elements à partir de 0.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6e6a0-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6e6a0-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6e6a0-116">Liste de $n $ qubits à laquelle la permutation est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6e6a0-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e6a0-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e6a0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="6e6a0-118">Références</span><span class="sxs-lookup"><span data-stu-id="6e6a0-118">References</span></span>

- [<span data-ttu-id="6e6a0-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, pp. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="6e6a0-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="6e6a0-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, springer link, pp. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="6e6a0-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="6e6a0-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e6a0-121">See Also</span></span>

- [<span data-ttu-id="6e6a0-122">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="6e6a0-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)