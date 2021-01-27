---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Opération MultiplyAndAddPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843058"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Opération MultiplyAndAddPhaseByModularInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Identique à MultiplyAndAddByModularInteger, mais suppose que opérande encode des entiers dans la base QFT.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="constmultiplier--int"></a>constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)

Entier $a $ à ajouter à chaque étiquette d’état de base.


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

Le modulo $N $, que l’addition et la multiplication sont prises en ce qui concerne.


### <a name="multiplier--littleendian"></a>multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique qui représente un entier non signé dont la valeur doit être ajoutée à chaque étiquette d’état de base de `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Registre quantique qui représente un entier non signé à utiliser comme cible pour cette opération.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Suppose que `phaseSummand` a le bit le plus élevé défini sur 0.
Suppose également que la valeur de `phaseSummand` est inférieure à $N $.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)