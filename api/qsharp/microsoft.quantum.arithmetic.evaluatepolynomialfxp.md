---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Opération EvaluatePolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707318"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="b6f2b-102">Opération EvaluatePolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="b6f2b-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="b6f2b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6f2b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6f2b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6f2b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6f2b-105">Évalue un polynomial dans une représentation à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="b6f2b-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="b6f2b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b6f2b-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="b6f2b-107">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b6f2b-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b6f2b-108">Coefficients du polynôme sous la forme d’un tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_d] $ pour le polynôme $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="b6f2b-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="b6f2b-109">FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b6f2b-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b6f2b-110">Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.</span><span class="sxs-lookup"><span data-stu-id="b6f2b-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="b6f2b-111">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b6f2b-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b6f2b-112">Nombre à virgule fixe de sortie qui contiendra $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="b6f2b-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="b6f2b-113">Doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b6f2b-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6f2b-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6f2b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

