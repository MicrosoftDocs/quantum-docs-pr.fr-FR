---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Opération EvaluateEvenPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707331"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="769db-102">Opération EvaluateEvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="769db-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="769db-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="769db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="769db-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="769db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="769db-105">Évalue un polynomial pair dans une représentation à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="769db-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="769db-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="769db-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="769db-107">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="769db-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="769db-108">Coefficients du polynôme pair sous la forme d’un tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_k] $ pour le $P polynomial pair (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.</span><span class="sxs-lookup"><span data-stu-id="769db-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="769db-109">FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="769db-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="769db-110">Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.</span><span class="sxs-lookup"><span data-stu-id="769db-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="769db-111">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="769db-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="769db-112">Nombre à virgule fixe de sortie qui contiendra $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="769db-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="769db-113">Doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="769db-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="769db-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="769db-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

