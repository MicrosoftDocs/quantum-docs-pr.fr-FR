---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203091"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="dc839-102">FastHadamardTransformed fonction)</span><span class="sxs-lookup"><span data-stu-id="dc839-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="dc839-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="dc839-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="dc839-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc839-105">Calcule la transformation Hadarmard d’une fonction booléenne dans {-1,1} l’encodage à l’aide de la méthode de Yates</span><span class="sxs-lookup"><span data-stu-id="dc839-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="dc839-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dc839-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="dc839-107">Func : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dc839-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dc839-108">Table de vérité en {-1,1} codage</span><span class="sxs-lookup"><span data-stu-id="dc839-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="dc839-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dc839-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dc839-110">Coefficients spectraux de la fonction</span><span class="sxs-lookup"><span data-stu-id="dc839-110">Spectral coefficients of the function</span></span>