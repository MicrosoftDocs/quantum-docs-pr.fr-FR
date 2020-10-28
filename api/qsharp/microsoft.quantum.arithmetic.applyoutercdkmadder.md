---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Opération ApplyOuterCDKMAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707574"
---
# <a name="applyoutercdkmadder-operation"></a>Opération ApplyOuterCDKMAdder

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Opération de transport d’ondulations sur place réversible qui est utilisée dans l’opération d’addition d’entiers RippleCarryAdderCDKM ci-dessous.
À partir de deux registres qubit `xs` et `ys` de la même longueur, l’opération applique une séquence d’ondulations de CNOTIN et CCNOT portes avec qubits dans `xs` et `ys` en tant que contrôles et qubits dans `xs` comme cibles.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Premier registre qubit, contenant les contrôles et les cibles.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Deuxième Registre qubit, qui contribue aux contrôles.


### <a name="ancilla--qubit"></a>Ancilla : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla qubit utilisé dans RippleCarryAdderCDKM passé à cette opération.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.
  https://arxiv.org/abs/quant-ph/0410184v1