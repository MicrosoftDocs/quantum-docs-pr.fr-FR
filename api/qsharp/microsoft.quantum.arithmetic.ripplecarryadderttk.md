---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Opération RippleCarryAdderTTK
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 45ba1b644166029ee548307cc1a7290c48e48a4b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221933"
---
# <a name="ripplecarryadderttk-operation"></a>Opération RippleCarryAdderTTK

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Les ondulations réversibles, sur place, ajoutent deux entiers.
Étant donné deux entiers $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , et un qubit Carry, l’opération calcule la somme des deux entiers où les bits les plus significatifs du $n sont conservés `ys` et le bit d’exécution est XOR au qubit `carry` .

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the First entier opérande.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir le $n les bits les moins significatifs de la somme.


### <a name="carry--qubit"></a>transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Transporter qubit, est XOR avec le bit le plus significatif de la somme.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération a les mêmes fonctionnalités que RippleCarryAdderD et, RippleCarryAdderCDKM, mais n’utilise aucune qubits Ancilla.

## <a name="references"></a>Références

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530