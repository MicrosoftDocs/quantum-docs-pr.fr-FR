---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Opération MultiplyFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706382"
---
# <a name="multiplyfxp-operation"></a>Opération MultiplyFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Multiplie deux nombres à virgule fixe dans des registres quantiques.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
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