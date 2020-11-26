---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Opération MultiplyAndAddPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223865"
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