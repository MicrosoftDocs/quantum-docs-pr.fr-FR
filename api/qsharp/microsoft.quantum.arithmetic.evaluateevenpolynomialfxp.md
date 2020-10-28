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
# <a name="evaluateevenpolynomialfxp-operation"></a>Opération EvaluateEvenPolynomialFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Évalue un polynomial pair dans une représentation à virgule fixe.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients du polynôme pair sous la forme d’un tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_k] $ pour le $P polynomial pair (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.


### <a name="fpx--fixedpoint"></a>FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.


### <a name="result--fixedpoint"></a>résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe de sortie qui contiendra $P (x) $. Doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

