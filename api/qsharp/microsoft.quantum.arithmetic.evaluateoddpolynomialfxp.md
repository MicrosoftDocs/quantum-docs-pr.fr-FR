---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Opération EvaluateOddPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223219"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="dfd51-102">Opération EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="dfd51-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="dfd51-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dfd51-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dfd51-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="dfd51-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="dfd51-105">Évalue un polynomial impair dans une représentation à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="dfd51-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dfd51-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dfd51-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="dfd51-107">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dfd51-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dfd51-108">Coefficients du polynôme impair sous forme de tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_k] $ pour la $P polynomiale irrégulière (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $.</span><span class="sxs-lookup"><span data-stu-id="dfd51-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="dfd51-109">FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="dfd51-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="dfd51-110">Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.</span><span class="sxs-lookup"><span data-stu-id="dfd51-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="dfd51-111">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="dfd51-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="dfd51-112">Nombre à virgule fixe de sortie qui contiendra P (x).</span><span class="sxs-lookup"><span data-stu-id="dfd51-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="dfd51-113">Doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="dfd51-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfd51-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfd51-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

