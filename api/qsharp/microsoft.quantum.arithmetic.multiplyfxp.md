---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Opération MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222607"
---
# <a name="multiplyfxp-operation"></a>Opération MultiplyFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplie deux nombres à virgule fixe dans des registres quantiques.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="fp1--fixedpoint"></a>FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Premier nombre à virgule fixe.


### <a name="fp2--fixedpoint"></a>FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Deuxième nombre à virgule fixe.


### <a name="result--fixedpoint"></a>résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe du résultat, doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’implémentation actuelle requiert que les trois nombres à virgule fixe aient la même position de point et le même nombre d’qubits.