---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Opération AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223780"
---
# <a name="assertmostsignificantbit-operation"></a>Opération AssertMostSignificantBit

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Déclare que le qubit le plus significatif d’un registre qubit qui représente un entier non signé est dans un état particulier.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="value--__invalidresult__"></a>valeur : __non <Result> valide__

Valeur du bit le plus élevé déclaré.


### <a name="number--littleendian"></a>nombre : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entier non signé dont le bit le plus élevé est vérifié.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

La version contrôlée de cette opération ignore les contrôles.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Intrinsic. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)