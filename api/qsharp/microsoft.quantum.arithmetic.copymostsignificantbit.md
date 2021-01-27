---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Opération CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843266"
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