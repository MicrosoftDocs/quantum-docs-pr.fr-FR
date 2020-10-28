---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Opération AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707451"
---
# <a name="assertmostsignificantbit-operation"></a>Opération AssertMostSignificantBit

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Déclare que le qubit le plus significatif d’un registre qubit qui représente un entier non signé est dans un état particulier.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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