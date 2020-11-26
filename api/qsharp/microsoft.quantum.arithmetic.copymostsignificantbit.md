---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Opération CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223287"
---
# <a name="copymostsignificantbit-operation"></a>Opération CopyMostSignificantBit

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Copie le bit le plus significatif d’un registre qubit `from` qui représente un entier non signé dans le qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="from--littleendian"></a>à partir de : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entier non signé à partir duquel le bit le plus élevé est copié.
l’entier est encodé au format Little endian.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit dans lequel le bit le plus élevé est copié. L’encodage de bits est basé sur le calcul.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)