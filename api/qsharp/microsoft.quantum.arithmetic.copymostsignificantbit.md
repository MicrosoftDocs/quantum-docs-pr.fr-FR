---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Opération CopyMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707339"
---
# <a name="copymostsignificantbit-operation"></a>Opération CopyMostSignificantBit

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Copie le bit le plus significatif d’un registre qubit `from` qui représente un entier non signé dans le qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
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