---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709158"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="a0b0e-102">FastHadamardTransformed fonction)</span><span class="sxs-lookup"><span data-stu-id="a0b0e-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="a0b0e-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a0b0e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a0b0e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0b0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0b0e-105">Calcule la transformation Hadarmard d’une fonction booléenne dans {-1,1} l’encodage à l’aide de la méthode de Yates</span><span class="sxs-lookup"><span data-stu-id="a0b0e-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a0b0e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a0b0e-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="a0b0e-107">Func : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a0b0e-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a0b0e-108">Table de vérité en {-1,1} codage</span><span class="sxs-lookup"><span data-stu-id="a0b0e-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="a0b0e-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a0b0e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a0b0e-110">Coefficients spectraux de la fonction</span><span class="sxs-lookup"><span data-stu-id="a0b0e-110">Spectral coefficients of the function</span></span>