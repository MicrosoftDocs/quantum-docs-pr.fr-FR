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
# <a name="evaluatepolynomialfxp-operation"></a>Opération EvaluatePolynomialFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Évalue un polynomial dans une représentation à virgule fixe.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients du polynôme sous la forme d’un tableau double, c’est-à-dire le tableau $ [a_0, a_1,..., a_d] $ pour le polynôme $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe d’entrée pour lequel évaluer le polynôme.


### <a name="result--fixedpoint"></a>résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe de sortie qui contiendra $P (x) $. Doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

