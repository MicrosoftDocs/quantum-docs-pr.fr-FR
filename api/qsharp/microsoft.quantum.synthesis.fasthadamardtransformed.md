---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855453"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="a842e-102">FastHadamardTransformed fonction)</span><span class="sxs-lookup"><span data-stu-id="a842e-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="a842e-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a842e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a842e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a842e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a842e-105">Calcule la transformation Hadarmard d’une fonction booléenne dans {-1,1} l’encodage à l’aide de la méthode de Yates</span><span class="sxs-lookup"><span data-stu-id="a842e-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a842e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a842e-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="a842e-107">Func : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a842e-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a842e-108">Table de vérité en {-1,1} codage</span><span class="sxs-lookup"><span data-stu-id="a842e-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="a842e-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a842e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a842e-110">Coefficients spectraux de la fonction</span><span class="sxs-lookup"><span data-stu-id="a842e-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="a842e-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="a842e-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```