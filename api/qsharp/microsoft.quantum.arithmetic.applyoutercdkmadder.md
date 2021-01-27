---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Opération ApplyOuterCDKMAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843703"
---
# <a name="applyoutercdkmadder-operation"></a>Opération ApplyOuterCDKMAdder

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Opération de transport d’ondulations sur place réversible qui est utilisée dans l’opération d’addition d’entiers RippleCarryAdderCDKM ci-dessous.
À partir de deux registres qubit `xs` et `ys` de la même longueur, l’opération applique une séquence d’ondulations de CNOTIN et CCNOT portes avec qubits dans `xs` et `ys` en tant que contrôles et qubits dans `xs` comme cibles.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
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