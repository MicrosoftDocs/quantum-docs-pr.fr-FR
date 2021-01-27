---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Opération CompareGreaterThanFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843323"
---
# <a name="comparegreaterthanfxp-operation"></a>Opération CompareGreaterThanFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Compare deux nombres à virgule fixe stockés dans des registres quantiques et contrôle un retournement sur le résultat.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="fp1--fixedpoint"></a>FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Premier nombre à virgule fixe à comparer.


### <a name="fp2--fixedpoint"></a>FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Deuxième nombre à virgule fixe à comparer.


### <a name="result--qubit"></a>résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Résultat de la comparaison. Est retourné si `fp1 > fp2` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’implémentation actuelle requiert que les deux nombres à virgule fixe aient la même position de point et le même nombre d’qubits.