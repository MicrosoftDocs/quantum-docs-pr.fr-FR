---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Opération RippleCarryAdderCDKM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: b08d8823fd539263205aca1ee15ee69adcb163b7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222097"
---
# <a name="ripplecarryaddercdkm-operation"></a>Opération RippleCarryAdderCDKM

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Les ondulations réversibles, sur place, ajoutent deux entiers.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Étant donné deux entiers $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , et un qubit Carry, l’opération calcule la somme des deux entiers où les bits les plus significatifs du $n sont conservés `ys` et le bit d’exécution est XOR au qubit `carry` .

## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the First entier opérande.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir les n bits les moins significatifs de la somme.


### <a name="carry--qubit"></a>transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Transporter qubit, est XOR avec le bit le plus significatif de la somme.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération a la même fonctionnalité que RippleCarryAdderD, mais utilise uniquement un qubit auxiliaire au lieu de $n $.

## <a name="references"></a>Références

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.
  https://arxiv.org/abs/quant-ph/0410184v1