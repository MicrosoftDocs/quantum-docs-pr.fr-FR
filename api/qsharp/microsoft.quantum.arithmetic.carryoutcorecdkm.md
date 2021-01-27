---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Opération CarryOutCoreCDKM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843344"
---
# <a name="carryoutcorecdkm-operation"></a>Opération CarryOutCoreCDKM

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


L’opération de base dans le RippleCarryAdderCDKM, utilisée avec l’opération ApplyOuterCDKMAdder ci-dessus, c’est-à-dire conjuguée avec cette opération pour obtenir le fonctionnement interne du RippleCarryAdderCDKM. Cette opération calcule le qubit d’exécution et applique une séquence de non-portes sur une partie de l’entrée `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Premier registre qubit.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Deuxième Registre qubit.


### <a name="ancilla--qubit"></a>Ancilla : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla qubit utilisé dans RippleCarryAdderCDKM passé à cette opération.


### <a name="carry--qubit"></a>transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Exécutez qubit dans l’opération RippleCarryAdderCDKM.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.
  https://arxiv.org/abs/quant-ph/0410184v1