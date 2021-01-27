---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Opération AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843425"
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