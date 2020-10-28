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
# <a name="evaluateoddpolynomialfxp-operation"></a>Opération EvaluateOddPolynomialFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Évalue un polynomial impair dans une représentation à virgule fixe.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients du polynôme impair sous forme de tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_k] $ pour la $P polynomiale irrégulière (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $.


### <a name="fpx--fixedpoint"></a>FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.


### <a name="result--fixedpoint"></a>résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe de sortie qui contiendra P (x). Doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

