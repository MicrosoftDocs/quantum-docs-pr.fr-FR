---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708846"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="17869-102">TruthTablesFromPermutationFolder fonction)</span><span class="sxs-lookup"><span data-stu-id="17869-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="17869-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="17869-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="17869-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17869-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17869-105">Logique de décomposition pour un index à une seule variable</span><span class="sxs-lookup"><span data-stu-id="17869-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="17869-106">Description</span><span class="sxs-lookup"><span data-stu-id="17869-106">Description</span></span>

<span data-ttu-id="17869-107">Cela prend l’état actuel et génère une permutation mise à jour et ajoute éventuellement de nouvelles fonctions pour les portes contrôlées.</span><span class="sxs-lookup"><span data-stu-id="17869-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="17869-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="17869-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="17869-109">numVars : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17869-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="17869-110">État : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="17869-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="17869-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17869-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="17869-112">Sortie : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="17869-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

