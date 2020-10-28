---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Opération ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709206"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="14efe-102">Opération ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="14efe-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="14efe-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="14efe-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="14efe-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14efe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14efe-105">Permute les amplitudes dans un État Quantum en fonction d’une permutation à l’aide d’une synthèse basée sur la décomposition.</span><span class="sxs-lookup"><span data-stu-id="14efe-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="14efe-106">Description</span><span class="sxs-lookup"><span data-stu-id="14efe-106">Description</span></span>

<span data-ttu-id="14efe-107">Cette opération est une version plus générale de @"microsoft.quantum.synthesis.applypermutationusingdecomposition" dans laquelle l’ordre des variables peut être spécifié.</span><span class="sxs-lookup"><span data-stu-id="14efe-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="14efe-108">Un ordre des variables différent modifie la séquence de décomposition et les tables de vérité utilisées pour les portes contrôlées @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="14efe-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="14efe-109">Par conséquent, la modification de l’ordre des variables modifie le nombre de portes globales utilisées pour réaliser la permutation.</span><span class="sxs-lookup"><span data-stu-id="14efe-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="14efe-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="14efe-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="14efe-111">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14efe-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14efe-112">Permutation de $2 ^ n $ Elements à partir de 0.</span><span class="sxs-lookup"><span data-stu-id="14efe-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="14efe-113">variableOrder : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14efe-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14efe-114">Permutation de $n $ Elements à partir de 0.</span><span class="sxs-lookup"><span data-stu-id="14efe-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="14efe-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="14efe-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="14efe-116">Liste de $n $ qubits à laquelle la permutation est appliquée.</span><span class="sxs-lookup"><span data-stu-id="14efe-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14efe-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14efe-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="14efe-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14efe-118">See Also</span></span>

- [<span data-ttu-id="14efe-119">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="14efe-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="14efe-120">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="14efe-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)