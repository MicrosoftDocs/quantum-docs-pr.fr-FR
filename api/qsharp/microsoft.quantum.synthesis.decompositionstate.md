---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Type défini par l’utilisateur DecompositionState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709170"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="a4bf3-102">Type défini par l’utilisateur DecompositionState</span><span class="sxs-lookup"><span data-stu-id="a4bf3-102">DecompositionState user defined type</span></span>

<span data-ttu-id="a4bf3-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a4bf3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a4bf3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4bf3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4bf3-105">État au cours de la décomposition en fonction d’index de variables</span><span class="sxs-lookup"><span data-stu-id="a4bf3-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="a4bf3-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="a4bf3-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="a4bf3-107">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a4bf3-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="a4bf3-108">Lfunctions : ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a4bf3-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="a4bf3-109">Rfunctions : ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a4bf3-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="a4bf3-110">Description</span><span class="sxs-lookup"><span data-stu-id="a4bf3-110">Description</span></span>

<span data-ttu-id="a4bf3-111">L’état contient la permutation actuelle et les fonctions actuellement générées pour les portes contrôlées à gauche, et les portes contrôlées à droite.</span><span class="sxs-lookup"><span data-stu-id="a4bf3-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>