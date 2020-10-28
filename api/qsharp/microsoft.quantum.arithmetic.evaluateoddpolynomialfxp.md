---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Opération EvaluateOddPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707326"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="e305e-102">Opération EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="e305e-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="e305e-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e305e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e305e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e305e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e305e-105">Évalue un polynomial impair dans une représentation à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="e305e-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="e305e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e305e-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="e305e-107">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e305e-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e305e-108">Coefficients du polynôme impair sous forme de tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_k] $ pour la $P polynomiale irrégulière (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $.</span><span class="sxs-lookup"><span data-stu-id="e305e-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="e305e-109">FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e305e-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e305e-110">Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.</span><span class="sxs-lookup"><span data-stu-id="e305e-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="e305e-111">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e305e-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e305e-112">Nombre à virgule fixe de sortie qui contiendra P (x).</span><span class="sxs-lookup"><span data-stu-id="e305e-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="e305e-113">Doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="e305e-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e305e-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e305e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

