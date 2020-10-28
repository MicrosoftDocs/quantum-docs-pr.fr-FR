---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Opération de multiplication
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706371"
---
# <a name="multiplyi-operation"></a>Opération de multiplication

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Multipliez `xs` l’entier par `ys` un entier et stockez le résultat dans `result` , qui doit être initialement égal à zéro.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n multiplicande $-bit (LittleEndian)


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n (LittleEndian)


### <a name="result--littleendian"></a>résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Utilise une approche standard Shift-and-Add pour implémenter la multiplication.
La version contrôlée a été améliorée par la copie des $x _i $ dans un Ancilla qubit conditionnel sur le qubits de contrôle, puis en contrôlant l’ajout sur le qubit Ancilla.