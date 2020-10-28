---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Opération CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707395"
---
# <a name="comparegreaterthanfxp-operation"></a>Opération CompareGreaterThanFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Compare deux nombres à virgule fixe stockés dans des registres quantiques et contrôle un retournement sur le résultat.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
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